<!-- NavBar.vue -->
<template>
  <header class="nav">
    <nav class="nav__inner" aria-label="Primary">
      <!-- Left: Logo -->
      <a href="/" class="nav__brand">
        <NuxtImg src="/logo-intellitoggle.png" alt="IntelliToggle" />
      </a>

      <!-- Center: Links -->
      <ul class="nav__links">
        <li><a href="/" class="is-active">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/pricing">Pricing</a></li>
      </ul>

      <!-- Right: CTA -->
      <a href="/sandbox" class="nav__cta">Start Sandbox</a>

      <!-- Mobile trigger -->
      <button class="nav__menu" @click="open = !open" aria-label="Toggle menu">
        <span></span><span></span><span></span>
      </button>
    </nav>

    <!-- Mobile drawer -->
    <div class="nav__drawer" v-show="open">
      <a href="/" @click="open=false">Home</a>
      <a href="/about" @click="open=false">About</a>
      <a href="/pricing" @click="open=false">Pricing</a>
      <a href="/sandbox" class="nav__cta--mobile" @click="open=false">Start Sandbox</a>
    </div>
  </header>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const open = ref(false)
</script>

<style scoped>
/* Bar */
.nav {
  position: sticky;
  top: 0;
  z-index: 50;
  background: #42389E; /* brand purple */
}

/* Inner row: paddings/heights by breakpoint */
.nav__inner {
  margin: 0 auto;
  width: 100%;
  display: grid;
  grid-template-columns: auto 1fr auto;
  align-items: center;
  column-gap: 24px;

  /* base (mobile) */
  height: 64px;
  padding: 0 16px;
}

/* >=768px */
@media (min-width: 768px) {
  .nav__inner {
    height: 80px;
    padding: 0 32px;
  }
}

/* >=1280px */
@media (min-width: 1280px) {
  .nav__inner {
    height: 112px;
    padding: 0 48px;
  }
}

/* >=1440px — match Figma (h 133, side padding 120) */
@media (min-width: 1440px) {
  .nav__inner {
    height: 133px;
    padding-left: 120px;
    padding-right: 120px;
    max-width: 1920px; /* keep page cap */
  }
}

/* Logo */
.nav__brand img {
  display: block;
  height: auto;
  width: 90px;
}
@media (min-width: 768px) { .nav__brand img { width: 160px; } }
@media (min-width: 1280px){ .nav__brand img { width: 184px; } }
@media (min-width: 1440px){ .nav__brand img { width: 205.5px; } }

/* Links (center) */
.nav__links {
  display: none;
  justify-content: center;
  align-items: center;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 24px;
}
@media (min-width: 768px) { .nav__links { display: flex; } }
@media (min-width: 1280px){ .nav__links { gap: 28px; } }
@media (min-width: 1440px){ .nav__links { gap: 27px; } }

.nav__links a {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  font-size: 14px;
  opacity: .9;
}
@media (min-width: 1024px){ .nav__links a { font-size: 16px; } }
@media (min-width: 1440px){ .nav__links a { font-size: 18px; } }

.nav__links a:is(:hover,:focus){ opacity: 1; }
.nav__links .is-active { font-weight: 600; opacity: 1; }

/* CTA (right) */
.nav__cta {
  display: none;
  align-items: center;
  justify-content: center;
  background: #F9A71E;
  color: #1F2555;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  box-shadow: 0 0 10px rgba(0,0,0,.05);
  height: 44px;
  padding: 8px 16px;
  transition: filter .15s ease;
}
.nav__cta:hover { filter: brightness(0.97); }

@media (min-width: 768px)  { .nav__cta { display: inline-flex; font-size: 14px; } }
@media (min-width: 1280px) { .nav__cta { height: 48px; padding: 10px 20px; font-size: 16px; } }
@media (min-width: 1440px) {
  .nav__cta { height: 53px; padding: 12px 24px; width: 214px; font-size: 18px; }
}

/* Mobile hamburger */
.nav__menu {
  justify-self: end;
  display: inline-flex;
  gap: 4px;
  flex-direction: column;
  background: transparent;
  border: 0;
  padding: 8px;
  margin-left: 10px;
  border-radius: 6px;
  cursor: pointer;
  color: #fff;
}
.nav__menu span {
  width: 22px; height: 2px; background: currentColor; display: block;
}
@media (min-width: 768px){ .nav__menu { display: none; } }

/* Mobile drawer */
.nav__drawer {
  display: grid;
  gap: 8px;
  padding: 12px 16px 16px;
  background: rgba(255,255,255,0.08);
  backdrop-filter: blur(6px);
}
.nav__drawer a {
  display: block;
  color: #fff;
  text-decoration: none;
  padding: 10px 12px;
  border-radius: 8px;
}
.nav__drawer a:hover { background: rgba(255,255,255,0.1); }
.nav__cta--mobile {
  background:#F9A71E; color:#1F2555; text-align:center; font-weight:600;
}
</style>
