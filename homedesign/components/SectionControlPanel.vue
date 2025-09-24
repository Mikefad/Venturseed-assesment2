<template>
  <section class="w-full p-6 pt-8">
    <!-- Frame 2147224116 -->
    <div
      class="what-it mx-auto flex w-full max-w-[1680px] flex-row items-center justify-between gap-[114px] px-0"
      style="min-height:624px"
    >
      <!-- LEFT: Frame 2147224106 -->
      <div class="what-it__left flex w-full max-w-[623px] flex-col ">
        <!-- Frame 2147224104 -->
        <div class="flex flex-col  w-full">
          <h2
            class="m-0 w-full mt-[55px] text-[25px] font-semibold text-[#0E121B]"
            style="font-family: Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Apple Color Emoji','Segoe UI Emoji','Segoe UI Symbol'"
          >
            Your AI Dart App’s Control Panel For Feature Releases
          </h2>
        </div>

        <!-- Frame 2147225952 -->
        <div class="flex w-full flex-col ">
          <p
            class="m-0 p-0 w-full text-[14px] font-normal text-[#5F5F60]"
            style="font-family: Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, 'Helvetica Neue', Arial, 'Noto Sans'"
          >
            IntelliToggle is a “Dart-Powered” feature flag that lets you turn features on/off instantly in your application without redeploying code. It allows you control roll-outs, run experiments, and fix bugs faster.
          </p>
        </div>

        <!-- Frame 2147224105 -->
        <div class="flex w-full flex-col ">
          <h3
            class="m-0 p-0 w-full text-[16px] font-semibold text-[#0E121B]"
            style="font-family: Inter, ui-sans-serif, system-ui"
          >
            Benefits
          </h3>

          <ul class="list-disc pl-5 m-0 space-y-0">
            <li class="text-[14px] text-[#5F5F60]" style="font-family: Inter">
              Toggle new features without app updates
            </li>
            <li class="text-[14px] text-[#5F5F60]" style="font-family: Inter">
              Roll out to specific users or regions
            </li>
            <li class="text-[14px] text-[#5F5F60]" style="font-family: Inter">
              Instantly rollback when needed
            </li>
          </ul>
        </div>
      </div>

      <!-- RIGHT: Frame 2147224115 -->
      <div
        class="what-it__right relative mx-auto flex h-[618px] w-full max-w-[830px] flex-col items-center justify-between rounded-[12px] shadow-[0_0_10px_10px_rgba(0,0,0,0.05)]"
        style="padding:46px 51px; background:linear-gradient(180deg,#42389E 0%, #0F1026 100%);"
      >
        <!-- flags (app mockup frame) -->
        <div class="what-it__stage relative mx-auto h-[517.69px] w-[728px] rounded-[4px] bg-[#F8F8F8] overflow-hidden">
          <img
            :src="mockup"
            alt="Feature flags dashboard mockup"
            class="what-it__screen absolute inset-0 m-auto max-h-full max-w-full object-contain"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// If the image is inside /assets, keep the import:
import mockup from '/Frame2147224116.png'
// If it's in /public use:
// const mockup = '/Frame2147224116.png'
</script>

<style scoped>
/* ---------- MOBILE-ONLY (≤480px) overrides to match your 345×564 frame ---------- */
@media (max-width: 480px) {
  .what-it {
    /* Frame 2147224116 */
    flex-direction: column;         /* stack */
    justify-content: center;
    align-items: flex-start;        /* left align */
    gap: 42px;                      /* figma gap */
    width: 345px;                   /* fixed frame width */
    max-width: 345px;
    margin-inline: auto;            /* center the frame on page */
    padding: 0;                     /* per figma */
    min-height: 564px;              /* visual parity */
  }

  .what-it__left {
    max-width: 100%;
  }

  .what-it__right {
    /* keep the gradient “device” but scale to the 345 frame */
    width: 345px;
    max-width: 345px;
    height: auto;
    padding: 20px 20px !important;  /* tighter padding for the small card */
  }

  .what-it__stage {
    /* inner light screen area */
    width: 100%;
    height: auto;
    aspect-ratio: 305 / 216;        /* looks like your screenshot proportions */
    border-radius: 4px;
  }

  .what-it__screen {
    position: absolute;
    inset: 0;
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
    margin: auto;
  }
}
</style>
