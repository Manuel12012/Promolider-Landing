<template>
  <svg width="0" height="0" style="position: absolute" aria-hidden="true">
    <symbol id="pl-mark" viewBox="0 0 200 220">
      <path
        d="M18 196 V14 H98 A62 62 0 0 1 98 138 H86"
        fill="none"
        stroke="currentColor"
        stroke-width="20"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M18 196 L74 112"
        fill="none"
        stroke="currentColor"
        stroke-width="20"
        stroke-linecap="round"
      />
      <path
        d="M54 80 L118 50 L114 118 Z"
        fill="currentColor"
        stroke="currentColor"
        stroke-width="8"
        stroke-linejoin="round"
      />
    </symbol>
    <symbol id="chev" viewBox="0 0 18 18">
      <path
        d="m6.6 3.6 6 5.4-6 5.4"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </symbol>
  </svg>

  <!-- ============ 01 HERO ============ -->
  <section class="hero" id="inicio" aria-labelledby="h1" data-video-host>
    <div class="crystal hero-fallback" aria-hidden="true">
      <div class="orb"><div class="caustic"></div></div>
      <div class="blade"></div>
      <div class="shine"></div>
    </div>

    <div class="tint"></div>

    <div class="frame">
      <header class="top">
        <a
          class="brand hx"
          style="--d: 0.05s"
          href="#top"
          aria-label="PROMOLIDER inicio"
        >
          <svg viewBox="0 0 200 220"><use href="#pl-mark" /></svg>
          PROMOLIDER
        </a>

        <div class="actions hx" style="--d: 0.2s">
          <nav class="ext" aria-label="Plataformas">
            <a
              href="https://vcr.promolider.org/login"
              target="_blank"
              rel="noopener"
            >
              Academia
              <svg viewBox="0 0 12 12" aria-hidden="true">
                <path
                  d="M3.5 8.5 8.5 3.5M4.5 3.5h4v4"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </a>
          </nav>

          <a
            class="cta"
            href="https://crm.promolider.org/login"
            target="_blank"
            rel="noopener"
          >
            <span class="t">Iniciar sesión</span>
            <span class="knob">
              <svg
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <circle cx="12" cy="8" r="4" />
                <path d="M4 21c1.2-4 4.2-6 8-6s6.8 2 8 6" />
              </svg>
            </span>
          </a>

          <button
            class="burger"
            type="button"
            aria-label="Abrir menú"
            aria-expanded="false"
            aria-controls="mmenu"
          >
            <i></i><i></i>
          </button>
        </div>

        <nav class="mmenu glass" id="mmenu" aria-label="Menú">
          <a href="#inicio">Inicio</a>
          <a href="#reflejo">El desafío</a>
          <a href="#cambio">La solución</a>
          <a href="#roles">Roles de la plataforma</a>
          <a href="#como">Cómo funciona</a>
          <a href="#primer-paso">Primer paso</a>
          <a href="#infraestructura">Infraestructura</a>
          <a href="#cocreacion">Modelo de colaboración</a>
          <a href="#cierre">Acceso a la plataforma</a>
          <hr />
          <a
            href="https://nft.promolider.org/"
            target="_blank"
            rel="noopener"
          >NFT</a>
          <a
            href="https://vcr.promolider.org/login"
            target="_blank"
            rel="noopener"
          >Academia</a>
          <a
            href="https://crm.promolider.org/login"
            target="_blank"
            rel="noopener"
          >Iniciar sesión</a>
        </nav>
      </header>

      <div class="mid" id="top">
        <div>
          <p class="eyebrow hx" style="--d: 0.3s">
            <b>PROMOLIDER™</b> — Plataforma de educación digital
          </p>

          <h1 id="h1">
            <span class="ln">
              <span class="ln-i" style="--d: 0.38s">
                Convierte tu conocimiento
              </span>
            </span>
            <span class="ln">
              <span class="ln-i" style="--d: 0.47s">
                en <strong>productos digitales</strong>
              </span>
            </span>
            <span class="ln">
              <span class="ln-i" style="--d: 0.56s">
                y contenido educativo.
              </span>
            </span>
          </h1>

          <div class="tagrow hx" style="--d: 0.75s">
            <span class="play" aria-hidden="true">
              <svg viewBox="0 0 13 14">
                <path d="M1.4 1.3 11.6 7 1.4 12.7z" fill="#0b1526" />
              </svg>
            </span>
            <span class="tag">
              Tecnología para crear y distribuir contenido digital.
            </span>
          </div>

          <p class="lead hx" style="--d: 0.85s">
            Promolider conecta conocimiento, herramientas tecnológicas y
            comercialización digital para facilitar la creación, publicación
            y distribución de cursos, masterclasses y otros productos
            educativos.
          </p>
        </div>

        <aside
          class="panel hx"
          style="--d: 0.8s"
          aria-label="Plataforma de educación digital"
        >
          <div class="row1">
            <span class="p-title">
              Educación<br />digital
              <span class="dot"></span>
            </span>
            <span class="seal" aria-hidden="true">
              <svg viewBox="0 0 200 220"><use href="#pl-mark" /></svg>
            </span>
          </div>

          <p class="p-sub">
            Herramientas para creadores.<br />
            Contenido educativo digital.
          </p>

          <div class="scale" aria-hidden="true">
            <span>01</span><span>02</span><span>03</span>
            <span>04</span><span>05</span>
          </div>

          <div class="track" aria-hidden="true"><i></i></div>

          <p class="cap">
            Crea · Publica · Distribuye · Comercializa · Gestiona
          </p>
        </aside>
      </div>

      <div class="bottom">
        <div class="stats" aria-label="Funciones de la plataforma">
          <div class="stat hx" style="--d: 0.95s">
            <span class="num">3</span>
            <span class="lbl">Áreas de<br />participación<br />en la plataforma</span>
          </div>

          <span class="slash hx" style="--d: 1s" aria-hidden="true"></span>

          <div class="stat hx" style="--d: 1.05s">
            <span class="num">5</span>
            <span class="lbl">Etapas de<br />gestión digital</span>
          </div>
        </div>

        <div class="hx" style="--d: 1.15s">
          <a class="meet js-cta" href="#roles">
            <span class="thumb" aria-hidden="true"></span>
            <b>Conocer cómo funciona la plataforma</b>
            <span class="knob">
              <svg><use href="#chev" /></svg>
            </span>
          </a>

          <p class="micro">
            Conoce las funciones y modalidades de participación.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Barra lateral de secciones -->
  <nav class="rail" id="rail" aria-label="Secciones de la página">
    <span class="thumb" aria-hidden="true"></span>

    <a href="#inicio" data-s="inicio" aria-label="01 · Inicio">
      <span class="tip">01 · Inicio</span>
    </a>
    <a href="#reflejo" data-s="reflejo" aria-label="02 · El desafío">
      <span class="tip">02 · El desafío</span>
    </a>
    <a href="#cambio" data-s="cambio" aria-label="03 · La solución">
      <span class="tip">03 · La solución</span>
    </a>
    <a href="#roles" data-s="roles" aria-label="04 · Roles de la plataforma">
      <span class="tip">04 · Roles de la plataforma</span>
    </a>
    <a href="#como" data-s="como" aria-label="05 · Cómo funciona">
      <span class="tip">05 · Cómo funciona</span>
    </a>
    <a href="#primer-paso" data-s="primer-paso" aria-label="06 · Primer paso">
      <span class="tip">06 · Primer paso</span>
    </a>
    <a
      href="#infraestructura"
      data-s="infraestructura"
      aria-label="07 · Infraestructura"
    >
      <span class="tip">07 · Infraestructura</span>
    </a>
    <a
      href="#cocreacion"
      data-s="cocreacion"
      aria-label="08 · Modelo de colaboración"
    >
      <span class="tip">08 · Modelo de colaboración</span>
    </a>
    <a href="#cierre" data-s="cierre" aria-label="09 · Acceso a la plataforma">
      <span class="tip">09 · Acceso a la plataforma</span>
    </a>
  </nav>
</template>