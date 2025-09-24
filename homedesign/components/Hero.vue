<!-- HeroWithVideo.vue -->
<script setup lang="ts">
// Banner (top half)
const banner = '/hero-banner.png'

// OPTION A: if you renamed vector to a space-free file in /public:
const vectorUrl = '/hero-vector.png'

// OPTION B: if your file has spaces or lives in /assets:
// const vectorUrl = useAsset('~/assets/images/Vector (2).png');
</script>

<template>
  <section class="relative w-full bg-white overflow-visible">
    <NuxtImg src="/hero-banner.png" alt="" preload class="hidden" aria-hidden="true" />

    <!-- TOP-HALF BANNER IMAGE -->
    <div
      class="absolute inset-x-0 top-0 -z-10 bg-cover bg-center"
      :style="{ height: '50vh', minHeight: '360px', backgroundImage: `url('${banner}')` }"
    />
    <!-- Contrast gradient over banner -->
    <div
      class="absolute inset-x-0 top-0 -z-10"
      :style="{ height: '50vh', minHeight: '360px', background: 'linear-gradient(180deg, rgba(0,0,0,.22) 0%, rgba(0,0,0,.06) 100%)' }"
    />

    <!-- CONTENT -->
    <div class="relative z-20 mx-auto max-w-[980px] px-6 pt-16 md:pt-24">
      <!-- DESKTOP: keep your existing markup -->
<div class="hidden md:block">
  <h1 class="text-white text-center text-3xl md:text-5xl font-bold leading-tight">
    The First <span class="bg-[#F9A71E] text-[#1A1C3D] px-2 rounded">Dart-Native</span>
    Feature Flag<br />With DartCodeAI
  </h1>

  <p class="mt-5 text-white/90 text-center md:text-lg">
    Feature flags built for Dart, ship faster, roll back safely, and scale with AI-powered delivery
    <br /><span class="font-semibold">Starting at just $1/month</span>
  </p>

  <div class="mt-3 text-center text-xs text-white/80">
    Valid till 15th September, 2025
  </div>

  <div class="mt-4 flex items-center justify-center gap-3">
    <button class="h-10 px-4 rounded bg-[#F9A71E] text-[#1A1C3D] font-semibold">
      Get Access
    </button>
    <button class="h-10 px-4 rounded border border-[#F9A71E] text-[#F9A71E] font-semibold">
      Join AI Early Access
    </button>
  </div>
</div>

<!-- MOBILE: exact Figma layout (345 × 345 frame) -->
<div class="md:hidden relative w-full">
  <div class="relative mx-auto w-[345px] h-[345px]">

    <!-- Title area 345×138 @ top:0 -->
    <!-- Title area 345×138 @ top:0 (one line + pill) -->
<div
  class="absolute left-0 top-0 w-[345px] h-[138px] flex justify-center text-white font-bold overflow-visible"
  style="font-family:Satoshi,ui-sans-serif; font-size:34px; line-height:46px; letter-spacing:-0.01em;"
>
  <div class="text-center">
    <!-- SINGLE LINE: The First + [pill] + Feature Flag With -->
    <span class="inline-flex items-center justify-center whitespace-nowrap leading-[46px]">
      <span>The First&nbsp;</span>

      <!-- yellow pill inline (201×56), nudged up -8px per Figma -->
      <span
        class="inline-flex items-center justify-center w-[201px] h-[56px] rounded-[8px] bg-[#F9A71E] px-[10px] py-[5px] translate-y-[-8px]"
        style="gap:10px;"
      >
        <span
          class="font-bold"
          style="
            width:181px; height:46px;
            font-family:Satoshi,ui-sans-serif; font-size:34px; line-height:46px; letter-spacing:-0.01em;
            background:linear-gradient(180deg,#42389E 0%, #0F1026 100%);
            -webkit-background-clip:text; -webkit-text-fill-color:transparent;
                    background-clip:text;         color:transparent;
            display:flex; align-items:center; justify-content:center; text-align:center;
          "
        >
          Dart-Native
        </span>
      </span>

      
    </span>
    <div>&nbsp;Feature Flag With</div>

    <!-- NEXT LINE -->
    <div class="leading-[46px]">DartCodeAI</div>
  </div>
</div>


    <!-- Subcopy 345×51 @ top:155 -->
    <p
      class="absolute left-0 top-[155px] w-[345px] h-[51px] flex items-center justify-center text-center text-white"
      style="font-family:Inter,ui-sans-serif; font-size:14px; line-height:17px; font-weight:400;"
    >
      Ship faster, control rollouts, and get ready for AI-powered delivery, starting at just $1/month for a limited time
    </p>

    <!-- CTAs frame 345×88 @ top:245 -->
    <div class="absolute left-0 top-[245px] w-[345px] h-[88px]">
      <!-- Primary button 345×40 @ top:0 -->
      <button
        class="absolute left-0 top-0 w-[345px] h-[40px] rounded-[5px] bg-[#F9A71E]"
        style="box-shadow:0px 4px 4px rgba(0,0,0,0.25);"
      >
        <span
          class="block text-center font-semibold"
          style="
            width:79px; height:17px; margin:11.5px auto 0;
            font-family:Inter,ui-sans-serif; font-size:14px; line-height:17px;
            background:linear-gradient(180deg,#42389E 0%, #0F1026 100%);
            -webkit-background-clip:text; -webkit-text-fill-color:transparent;
                    background-clip:text;         color:transparent;
          "
        >
          Get Started
        </span>
      </button>

      <!-- Secondary button 345×40 @ top:48 -->
      <button
        class="absolute left-0 top-[48px] w-[345px] h-[40px] rounded-[5px] border border-[#F9A71E]"
        style="filter:drop-shadow(0px 4px 4px rgba(0,0,0,0.25));"
      >
        <span
          class="block text-center font-semibold text-[#F9A71E]"
          style=" height:17px; margin:11.5px auto 0; font-family:Inter,ui-sans-serif; font-size:14px; line-height:17px;"
        >
          Learn More
        </span>
      </button>
    </div>
  </div>

  <!-- (Optional) show the “Valid till …” note under the frame on mobile -->
  
</div>


      <!-- spacer so content fits inside banner area -->
      <div class="pb-5 md:pb-12"></div>

      <!-- YouTube card (single, correct block) -->
      <!-- Replace ONLY this block -->
<div
  class="mt-6 md:mt-10 mx-auto
         w-[294px] h-[209px]          /* mobile size */
         md:w-full md:max-w-[980px]   /* desktop/tablet size */
         md:h-[520px]
         bg-white rounded-[12px] border border-[#99A0AE]
         shadow-[0_0_10px_10px_rgba(0,0,0,0.05)]
         relative overflow-hidden"
>
  <a
    href="javascript:void(0)"
    class="absolute inset-0 grid place-items-center group outline-none"
    aria-label="Play video"
  >
    <span
      class="inline-grid place-items-center
             w-[64px] h-[46px]           /* smaller play badge on mobile */
             md:w-[88px] md:h-[64px]
             rounded-[12px] bg-[#E70000]
             ring-0 group-focus-visible:ring-4 ring-[#E70000]/30 transition-transform
             group-hover:scale-105"
    >
      <svg width="24" height="24" viewBox="0 0 30 30" aria-hidden="true" class="md:w-[30px] md:h-[30px]">
        <path d="M10 7 L24 15 L10 23 Z" fill="#ffffff"/>
      </svg>
    </span>
  </a>
</div>
</div>


    <!-- VECTOR that “cuts” the section -->
    <NuxtImg
      :src="vectorUrl"
      alt=""
      class="pointer-events-none select-none absolute inset-x-0 -z-0 h-[700px] md:h-auto"
      style="top: calc(0vh - 40px); width: 100%; display: block; object-fit: cover;"
      loading="lazy"
    />

    
  </section>
</template>

<style scoped>
/* Mobile-only override for the YouTube card using your Figma properties */
@media (max-width: 480px) {
  .yt-card {
    position: absolute !important;
    width: 294px !important;
    height: 209px !important;
    left: calc(50% - 294px / 2 + 5.5px) !important; /* centers + 5.5px */
    top: 481px !important;

    /* background image + drop shadow per spec */
    background:
      url("/Frame2147224103.png") center / cover no-repeat,
      #ffffff;
    box-shadow: 0px 0px 10px 10px rgba(0, 0, 0, 0.05) !important;

    /* keep your existing rounding/border */
    border-radius: 12px !important;
    border: 1px solid #99A0AE !important;
  }
}
</style>