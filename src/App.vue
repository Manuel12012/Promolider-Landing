<script setup>
import { onMounted, onBeforeUnmount } from "vue";

import Cambio from "./components/Cambio.vue";
import Cierre from "./components/Cierre.vue";
import CoCreacion from "./components/CoCreacion.vue";
import Como from "./components/Como.vue";
import Footer from "./components/Footer.vue";
import Hero from "./components/Hero.vue";
import Infraestructura from "./components/Infraestructura.vue";
import PrimerPaso from "./components/PrimerPaso.vue";
import Reflejo from "./components/Reflejo.vue";
import Roles from "./components/Roles.vue";

let cleanup = [];

onMounted(() => {
  const reduced = window.matchMedia("(prefers-reduced-motion: reduce)").matches;

  /*
   * ============================================================
   * AÑO DEL FOOTER
   * ============================================================
   */

  const year = document.getElementById("year");

  if (year) {
    year.textContent = new Date().getFullYear();
  }

  /*
   * ============================================================
   * CTA
   * ============================================================
   */

  const ctas = document.querySelectorAll(".js-cta");

  // funcion
  const handleCta = (event) => {
    const link = event.currentTarget;

    if (link.getAttribute("href") === "#") {
      event.preventDefault();
    }
  };

  ctas.forEach((cta) => {
    cta.addEventListener("click", handleCta);

    cleanup.push(() => {
      cta.removeEventListener("click", handleCta);
    });
  });

  /*
   * ============================================================
   * FADE / INTERSECTION OBSERVER
   * ============================================================
   */

  const fadeElements = document.querySelectorAll(".fade");

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("visible");
          observer.unobserve(entry.target);
        }
      });
    },
    {
      threshold: 0.18,
    },
  );

  fadeElements.forEach((element) => {
    observer.observe(element);
  });

  cleanup.push(() => {
    observer.disconnect();
  });

  /*
   * ============================================================
   * CAMBIO — GRÁFICAS
   * ============================================================
   */

  const meters = document.querySelectorAll(".pair .meter");

  if (meters.length >= 2) {
    const [beforeMeter, afterMeter] = meters;

    for (let i = 0; i < 18; i++) {
      // ANTES
      const beforeBar = document.createElement("i");

      beforeBar.style.setProperty("--h", `${25 + Math.random() * 75}%`);

      beforeBar.style.animationDelay = `${(Math.random() * 3).toFixed(2)}s`;

      beforeMeter.appendChild(beforeBar);

      // AHORA
      const afterBar = document.createElement("i");

      afterBar.style.setProperty("--h", `${6 + Math.pow(i / 17, 1.3) * 94}%`);

      afterBar.style.transitionDelay = `${i * 0.05}s`;

      afterMeter.appendChild(afterBar);
    }
  }

  /*
   * ============================================================
   * RAIL LATERAL
   * ============================================================
   */

  const rail = document.getElementById("rail");

  if (rail) {
    const thumb = rail.querySelector(".thumb");
    const railLinks = [...rail.querySelectorAll("a")];

    const sections = railLinks
      .map((link) => document.getElementById(link.dataset.s))
      .filter(Boolean);

    const updateRail = () => {
      const mark = window.innerHeight * 0.45;

      let activeIndex = 0;

      sections.forEach((section, index) => {
        if (section.getBoundingClientRect().top <= mark) {
          activeIndex = index;
        }
      });

      // Si llegamos al final de la página
      if (
        window.innerHeight + window.scrollY >=
        document.documentElement.scrollHeight - 4
      ) {
        activeIndex = sections.length - 1;
      }

      railLinks.forEach((link, index) => {
        const active = index === activeIndex;

        link.classList.toggle("on", active);

        if (active) {
          link.setAttribute("aria-current", "true");
        } else {
          link.removeAttribute("aria-current");
        }
      });

      if (thumb && railLinks[activeIndex]) {
        thumb.style.top = `${railLinks[activeIndex].offsetTop}px`;
      }
    };

    updateRail();

    window.addEventListener("scroll", updateRail, { passive: true });

    window.addEventListener("resize", updateRail);

    cleanup.push(() => {
      window.removeEventListener("scroll", updateRail);

      window.removeEventListener("resize", updateRail);
    });
  }

  /*
   * ============================================================
   * MENÚ MÓVIL
   * ============================================================
   */

  const burger = document.querySelector(".burger");

  const mobileMenu = document.getElementById("mmenu");

  if (burger && mobileMenu) {
    const setMenu = (open) => {
      mobileMenu.classList.toggle("open", open);

      burger.setAttribute("aria-expanded", String(open));

      burger.setAttribute("aria-label", open ? "Cerrar menú" : "Abrir menú");
    };

    const handleBurgerClick = (event) => {
      event.stopPropagation();

      const isOpen = mobileMenu.classList.contains("open");

      setMenu(!isOpen);
    };

    const handleDocumentClick = (event) => {
      if (!mobileMenu.contains(event.target)) {
        setMenu(false);
      }
    };

    const handleEscape = (event) => {
      if (event.key === "Escape") {
        setMenu(false);
      }
    };

    const menuLinks = mobileMenu.querySelectorAll("a");

    const handleMenuLinkClick = () => {
      setMenu(false);
    };

    burger.addEventListener("click", handleBurgerClick);

    document.addEventListener("click", handleDocumentClick);

    document.addEventListener("keydown", handleEscape);

    menuLinks.forEach((link) => {
      link.addEventListener("click", handleMenuLinkClick);
    });

    cleanup.push(() => {
      burger.removeEventListener("click", handleBurgerClick);

      document.removeEventListener("click", handleDocumentClick);

      document.removeEventListener("keydown", handleEscape);

      menuLinks.forEach((link) => {
        link.removeEventListener("click", handleMenuLinkClick);
      });
    });
  }

  /*
   * ============================================================
   * EL CÓMO — PASOS ANIMADOS
   * ============================================================
   */

  const flowSteps = [...document.querySelectorAll(".fstep")];

  let flowIndex = 0;
  let flowInterval = null;

  if (flowSteps.length) {
    const activateStep = () => {
      flowSteps.forEach((step, index) => {
        step.classList.toggle("on", index === flowIndex);
      });

      flowIndex = (flowIndex + 1) % flowSteps.length;
    };

    activateStep();

    if (!reduced) {
      flowInterval = window.setInterval(activateStep, 2200);

      cleanup.push(() => {
        clearInterval(flowInterval);
      });
    }
  }

  /*
   * ============================================================
   * CO-CREACIÓN — PALABRAS
   * ============================================================
   */

  const wordsContainer = document.getElementById("words");

  if (wordsContainer) {
    const text = wordsContainer.textContent.trim();

    wordsContainer.innerHTML = text
      .split(/\s+/)
      .map(
        (word, index) =>
          `<span class="w${
            index >= 9 && index <= 14 ? " g" : ""
          }">${word}</span>`,
      )
      .join(" ");

    const words = [...wordsContainer.querySelectorAll(".w")];

    const updateWords = () => {
      const rect = wordsContainer.getBoundingClientRect();

      const progress = Math.max(
        0,
        Math.min(
          1,
          (window.innerHeight * 0.85 - rect.top) /
            (rect.height + window.innerHeight * 0.35),
        ),
      );

      const count = Math.round(progress * words.length);

      words.forEach((word, index) => {
        word.classList.toggle("on", index < count);
      });
    };

    if (reduced) {
      words.forEach((word) => {
        word.classList.add("on");
      });
    } else {
      updateWords();

      window.addEventListener("scroll", updateWords, { passive: true });

      cleanup.push(() => {
        window.removeEventListener("scroll", updateWords);
      });
    }
  }
});

onBeforeUnmount(() => {
  cleanup.forEach((fn) => fn());
  cleanup = [];
});
</script>

<template>
  <Hero />

  <Reflejo />

  <Cambio />

  <Roles />

  <Como />

  <PrimerPaso />

  <Infraestructura />

  <CoCreacion />

  <Cierre />

  <Footer />
</template>
