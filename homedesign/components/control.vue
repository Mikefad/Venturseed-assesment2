<script setup lang="ts">

const connectImg = '/connect.png';
const flagsImg = '/flags.png';
const shipImg = '/ship.png';

type Item = {
  title: string
  desc: string
  img?: string
  alt?: string
  href?: string
}

const props = defineProps<{ items?: Item[] }>()

const fallback: Item[] = [
  {
    title: 'Connect',
    desc: 'Install SDK in your Dart project in 2 mins.',
    img: connectImg,
    alt: 'Connect preview',
    href: '#',
  },
  {
    title: 'Create Flags',
    desc: 'Define features in IntelliToggle dashboard.',
    img: flagsImg,
    alt: 'Create flags preview',
    href: '#',
  },
  {
    title: 'Ship & Control',
    desc: 'Flip switches anytime, see instant results.',
    img: shipImg,
    alt: 'Ship and control preview',
    href: '#',
  },
]

const items = computed(() => props.items ?? fallback)
</script>

<template>
  <!-- OUTER: full width, centered content -->
  <section class="w-full py-24 ml-[5px] md:py-28">
    <!-- CONTAINER: center and cap width so it doesn't overflow -->
    <div class="mx-auto max-w-[1680px] px-6 md:px-10">
      <h2 class="text-center text-3xl md:text-5xl font-semibold text-[#1A1C3D]">
        Control &amp; Power-focused
      </h2>

      <!-- ROW: responsive grid, centered, preserves 95px gap on large -->
      <div
        class="mt-12 grid justify-items-center gap-10 lg:gap-[95px] sm:grid-cols-2 xl:grid-cols-3"
      >
        <article
          v-for="(card, i) in items"
          :key="i"
          class="flex w-full max-w-[497px] flex-col gap-8"
        >
          <!-- PREVIEW -->
          <div class="flex flex-col">
            <div class="relative w-full aspect-[497/363] rounded-[12px] bg-[#1A1C3D] overflow-hidden">
              <!-- Mock surface to match design -->
              <div class="absolute left-[15.5px] top-[11.71px] right-[15.5px] bottom-[13.5px] rounded bg-[#F8F8F8]"></div>
              <div class="absolute left-0 top-[26.39px] w-[89.72px] h-[calc(100%-26.39px-25px)] bg-white"></div>

              <NuxtImg
                v-if="card.img"
                :src="card.img"
                :alt="card.alt || card.title"
                class="absolute inset-0 h-full w-full object-cover opacity-80"
                loading="lazy"
              />
            </div>
          </div>

          <!-- TEXT + CTA -->
          <div class="flex flex-col gap-2">
            <h3 class="text-[22px] md:text-[24px] leading-[29px] font-semibold text-[#1A1C3D]">
              {{ card.title }}
            </h3>
            <p class="text-[16px] md:text-[18px] leading-[22px] text-[#5F5F60]">
              {{ card.desc }}
            </p>

            <NuxtLink
              :to="card.href || '#'"
              class="mt-4 inline-flex items-center justify-center gap-2 px-6 py-3 h-[46px] w-[243px] rounded-lg border border-[#F9A71E] shadow-[0_0_10px_10px_rgba(0,0,0,0.05)] text-[18px] leading-[22px] text-[#F9A71E]"
            >
              View Documentation
            </NuxtLink>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
