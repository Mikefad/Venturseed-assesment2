<template>
  <section class="relative w-full bg-white overflow-x-hidden mt-10">
    <div
      class="mx-auto flex w-full max-w-[1920px] flex-col items-center
             gap-[40px] px-6 xl:px-[120px] h-auto md:h-[369px] mt-6"
    >
      <h3
        class="m-0 text-center font-semibold text-[#1A1C3D] text-[14px] md:text-[24px] w-auto h-auto"
        style="font-family:Inter,system-ui,sans-serif; line-height:29px;"
      >
        Trusted by various engineering teams
      </h3>

      <div
        class="mx-auto flex h-[60px] w-full max-w-[1035.27px] items-center
               justify-center gap-[40px] md:gap-[100px]"
      >
        <div
          v-for="(b, i) in brands"
          :key="b.name"
          class="flex shrink-0 items-center justify-center"
          :style="{ width: b.w + 'px', height: '60px' }"
        >
          <img
            :src="b.src"
            :alt="b.name"
            class="block h-full w-auto object-contain"
            v-show="!imgFailed[i]"
            @error="imgFailed[i] = true"
            style="opacity:.9;"
          />
          <span
            v-show="imgFailed[i]"
            class="inline-flex h-[60px] items-center justify-center whitespace-nowrap text-[#1A1C3D]/90"
            style="font-family:Inter,system-ui,sans-serif;font-size:18px;line-height:22px;"
          >
            {{ b.name }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

// Helper so filenames with spaces/() still work
const pub = (path: string) => encodeURI(path)

const brands = [
  { name: 'Google Cloud',        src: pub('/Frame 1618872620.png'), w: 155.27 },
  { name: 'Amazon Web Services', src: pub('/amazon_aws-ar21 1.png'), w: 120 },
  { name: 'Microsoft Azure',     src: pub('/Group (2).png'),        w: 120 },
  { name: 'DigitalOcean',        src: pub('/google.png'),           w: 120 },
  { name: 'IBM',                 src: pub('/Vector (8).png'),       w: 120 },
]

const imgFailed = ref<Record<number, boolean>>({})
</script>
