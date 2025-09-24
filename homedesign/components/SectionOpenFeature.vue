<!-- SectionOpenFeature.vue -->
<template>
  <!-- Frame 2147224284 -->
  <section class="w-full bg-[#EDECF6] pl-[10px] pt-[55px]" data-of>
    <div class="mx-auto flex w-full max-w-[1920px] flex-col items-center gap-[56px] mt-[50px] px-6 py-[120px]">
      <!-- Frame 2147224083 -->
      <div class="mx-auto flex w-full max-w-[1680px] flex-col items-center justify-between gap-[160px] lg:flex-row">
        <!-- LEFT -->
        <div
          class="relative mx-auto flex h-[618px] w-full max-w-[830px] items-center justify-center rounded-[12px] bg-white shadow-[0_0_10px_10px_rgba(0,0,0,0.05)]"
          style="padding:77px 71px"
        >
          <img
            :src="openFeatureImg"
            alt="OpenFeature"
            class="max-h-full max-w-full object-contain rounded-[10px] ring-1 ring-[#42389E]/30"
          />
        </div>

        <!-- RIGHT -->
        <div class="mx-auto flex w-full max-w-[575px] flex-col gap-8">
          <div class="flex flex-col gap-4">
            <h2
              class="text-[32px]/[39px] font-semibold text-[#0E121B]"
              style="font-family: Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, 'Helvetica Neue', Arial"
            >
              Seamless Feature Management with OpenFeature
            </h2>
            <p
              class="text-[18px]/[22px] text-[#5F5F60]"
              style="font-family: Inter, ui-sans-serif, system-ui"
            >
              Aortem now integrates with OpenFeature to provide developers with a powerful, standardized
              approach to feature flagging and dynamic configuration. Ship features faster, test safely,
              and optimize user experiences effortlessly.
            </p>
          </div>

          <button
            type="button"
            class="group inline-flex h-[48px] w-[194px] items-center justify-center gap-[10px] rounded-[8px] bg-[#F9A71E] px-6 py-3 shadow-[0_4px_4px_rgba(0,0,0,0.25)]"
          >
            <span
              class="text-[20px]/[23px] font-bold"
              style="
                font-family: 'Merriweather Sans', ui-sans-serif, system-ui;
                background: linear-gradient(180deg,#42389E 0%, #0F1026 100%);
                -webkit-background-clip: text; background-clip: text;
                -webkit-text-fill-color: transparent;
              "
            >
              Learn More
            </span>
            <svg class="h-6 w-6 transition-transform group-hover:translate-x-0.5" viewBox="0 0 24 24" fill="none">
              <path d="M8 12h8M13 7l5 5-5 5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import openFeatureImg from '/openfeature-stacked-black.png'
</script>

<style scoped>
/* MOBILE ONLY (≤480px): remove bg + center layout */
@media (max-width: 480px) {
  /* remove purple background */
  section[data-of] { background: transparent !important; }

  /* tighten outer padding/gap */
  section[data-of] > .mx-auto { padding: 0 !important; gap: 0 !important; }

  /* center the inner column (no 24px left offset) */
  section[data-of] .mx-auto.flex.w-full.max-w-\[1680px\] {
    width: 345px !important;
    max-width: 345px !important;
    margin: 0 auto !important;       /* centered */
    padding: 0 !important;
    flex-direction: column !important;
    align-items: center !important;   /* centered */
    gap: 21px !important;
  }

  /* logo card */
  section[data-of] .bg-white.rounded-\[12px\] {
    width: 345px !important;
    height: 303px !important;
    padding: 77px 71px !important;
    border: 1px solid rgba(66,72,158,0.2) !important;
    border-radius: 16px !important;
    box-shadow: none !important;
    gap: 10px !important;
  }
  section[data-of] .bg-white.rounded-\[12px\] img {
    width: 209px !important;
    height: 106px !important;
    object-fit: contain !important;
    --tw-ring-shadow: 0 0 #0000 !important;
    --tw-ring-offset-shadow: 0 0 #0000 !important;
  }

  /* text column + spacing */
  section[data-of] .max-w-\[575px\] {
    width: 345px !important;
    max-width: 345px !important;
    gap: 32px !important;
  }
  section[data-of] .max-w-\[575px\] > .flex.flex-col.gap-4 { gap: 16px !important; }

  /* typography */
  section[data-of] h2 { font-size: 18px !important; line-height: 22px !important; font-weight: 600 !important; color: #1B1D22 !important; margin: 0 !important; }
  section[data-of] p  { font-size: 14px !important; line-height: 17px !important; color: #5F5F60 !important; margin: 0 !important; }

  /* CTA bar */
  section[data-of] button.group {
    width: 345px !important; height: 40px !important;
    padding: 24px 36px !important; border-radius: 5px !important;
    background: linear-gradient(180deg,#42389E 0%,#0F1026 100%) !important;
    box-shadow: 0 4px 4px rgba(0,0,0,0.25) !important; gap: 10px !important;
  }
  section[data-of] button.group span {
    font-family: 'Merriweather Sans', ui-sans-serif, system-ui !important;
    font-size: 14px !important; line-height: 23px !important; font-weight: 700 !important;
    background: none !important; -webkit-text-fill-color: #fff !important; color: #fff !important;
  }
  section[data-of] button.group svg { width: 24px !important; height: 24px !important; color: #fff !important; }
}
</style>
