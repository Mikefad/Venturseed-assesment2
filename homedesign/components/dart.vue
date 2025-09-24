<script setup lang="ts">
type Row = { feature: string; it: boolean; other: boolean }

const rows: Row[] = [
  { feature: 'Dart-native SDK & server', it: true, other: false },
  { feature: 'End-to-end type safety', it: true, other: false },
  { feature: 'AI-assisted roll-outs & cleanup', it: true, other: false },
  { feature: 'A/B testing built-in', it: true, other: false },
  { feature: 'Dart-Powered SDKs', it: true, other: false },
]
</script>

<template>
  <section class="w-full py-28 md:py-32 flex flex-col items-center gap-8">
    <!-- Title block -->
    <div class="w-full max-w-[1680px] px-6 md:px-10 flex flex-col items-center gap-12">
      <div class="flex flex-col items-center gap-2 max-w-[826px]">
        <h2
          class="text-center text-[40px] leading-[54px] font-bold bg-gradient-to-b from-[#42389E] to-[#0F1026] bg-clip-text text-transparent"
        >
          Dart-Powered Feature Flag
        </h2>

        <div class="flex flex-col items-center gap-2">
          <h3 class="text-center text-[32px] leading-[39px] font-semibold text-[#1A1C3D]">
            Not Another Generic Feature Flag Tool
          </h3>
          <p class="text-center text-[18px] leading-[22px] text-[#5F5F60]">
            Most tools are built for every language, which means extra layers and slower toggles.
            IntelliToggle is built in Dart, for Dart — so it’s faster, safer, and built for your stack.
          </p>
        </div>
      </div>

      <!-- Table -->
      <div class="w-full flex justify-center">
        <div
          class="w-full max-w-[1440px] rounded-lg shadow-[0_0_10px_10px_rgba(0,0,0,0.05)] overflow-hidden bg-[#EDECF6]"
        >
          <!-- Header -->
          <div
            class="grid grid-cols-[1fr,220px,220px] md:grid-cols-[1fr,1fr,1fr] h-[50px] items-center bg-gradient-to-b from-[#42389E] to-[#0F1026] text-white"
          >
            <div class="px-4 md:px-6 text-[24px] leading-[29px] font-semibold">Features</div>
            <div class="px-4 md:px-6 text-center text-[24px] leading-[29px] font-semibold">
              IntelliToggle
            </div>
            <div class="px-4 md:px-6 text-center text-[24px] leading-[29px] font-semibold">
              Other Feature Flag
            </div>
          </div>

          <!-- Rows -->
          <!-- MOBILE SCROLLER WRAP -->
<div class="md:mx-0 -mx-6">
  <div
    class="block md:overflow-visible overflow-x-auto whitespace-nowrap scrollbar-hide"
    style="-webkit-overflow-scrolling:touch"
  >
    <!-- Force a width wider than small screens so it can scroll -->
    <div class="min-w-[760px] md:min-w-0">
      <div class="divide-y divide-black/5">
        <div
          v-for="(r, i) in rows"
          :key="i"
          class="grid grid-cols-[1fr,220px,220px] md:grid-cols-[1fr,1fr,1fr]
                 h-[50px] items-center bg-[#EDECF6]"
        >
          <div class="px-4 md:px-6 text-[18px] leading-[22px] font-semibold text-[#5F5F60]">
            {{ r.feature }}
          </div>

          <div class="px-4 md:px-6 flex justify-center">
            <svg v-if="r.it" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                 class="h-5 w-5" fill="none" stroke="#1B1D22" stroke-width="1.5"
                 stroke-linecap="round" stroke-linejoin="round">
              <path d="M20 6L9 17l-5-5" />
            </svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                 class="h-5 w-5" fill="none" stroke="#1B1D22" stroke-width="1.5"
                 stroke-linecap="round" stroke-linejoin="round">
              <path d="M18 6L6 18M6 6l12 12" />
            </svg>
          </div>

          <div class="px-4 md:px-6 flex justify-center">
            <svg v-if="r.other" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                 class="h-5 w-5" fill="none" stroke="#1B1D22" stroke-width="1.5"
                 stroke-linecap="round" stroke-linejoin="round">
              <path d="M20 6L9 17l-5-5" />
            </svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                 class="h-5 w-5" fill="none" stroke="#1B1D22" stroke-width="1.5"
                 stroke-linecap="round" stroke-linejoin="round">
              <path d="M18 6L6 18M6 6l12 12" />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

          <!-- Rounded bottom on container matches figma -->
          <div class="h-0 rounded-b-[12px]"></div>
        </div>
      </div>
    </div>
  </section>
</template>
