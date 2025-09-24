<script setup lang="ts">
// Background image (already working)
const aijpg = '/ai.jpg'

type Card = { title: string; desc: string; iconSrc: string; alt: string }

const topRow: Card[] = [
  {
    iconSrc: '/lets-icons_flag-fill.png',
    alt: 'AutoFlag icon',
    title: 'AutoFlag AI (LLM-Assisted Flag Creation)',
    desc:
      'Create new flags just by typing what you need. The AI names it, sets rules, and configures targeting for you.',
  },
  {
    iconSrc: '/ic_round-smart-toy.png',
    alt: 'SmartRamp icon',
    title: 'SmartRamp AI (AI-Driven Rollout Optimization)',
    desc:
      'Rollouts that adjust themselves. AI expands, pauses, or rolls back based on real-time metrics.',
  },
]

const bottomRow: Card[] = [
  {
    iconSrc: '/mingcute_search-ai-fill.png',
    alt: 'ExplainFlags icon',
    title: 'ExplainFlags AI (LLM Root-Cause + Insights)',
    desc:
      'Understand issues instantly with AI-generated, plain-language insights tied to your flags.',
  },
  {
    iconSrc: '/ph_line-segments-fill.png',
    alt: 'AutoSegment icon',
    title: 'AutoSegment AI (Behavioral Segmentation)',
    desc:
      'Target the right users automatically. AI builds segments from live behavior—no manual rules.',
  },
]
</script>

<template>
  <!-- SECTION -->
  <section
    class="relative w-full flex flex-col items-center justify-between gap-12 px-6 md:px-10 py-28 md:py-32 overflow-hidden"
  >
    <!-- background image -->
    <div
      class="absolute inset-0 z-0 bg-cover bg-center"
      :style="{ backgroundImage: `url(${aijpg})` }"
    />
    <!-- gradient overlay -->
    <div
      class="absolute inset-0 z-10 pointer-events-none"
      style="background: linear-gradient(180deg, rgba(66,56,158,0.8) 0%, rgba(26,28,61,0.8) 100%);"
    />

    <!-- Header -->
    <div class="relative z-20 w-full max-w-[1680px] mx-auto flex flex-col items-center gap-2">
      <div class="px-8 py-2 rounded-full bg-[#F9A71E] text-center">
        <span
          class="text-[18px] leading-[22px] font-semibold bg-gradient-to-b from-[#42389E] to-[#0F1026] bg-clip-text text-transparent"
        >
          Coming Soon
        </span>
      </div>
      <h2 class="text-center text-white text-[40px] leading-[54px] font-bold mt-4">
        DartCodeAI That Actually Changes Flagging
      </h2>
    </div>

    <!-- Cards -->
    <div class="relative z-20 w-full max-w-[1680px] mx-auto flex flex-col gap-8">
      <!-- row 1 -->
      <div class="mx-auto w-full max-w-[1440px] grid grid-cols-1 lg:grid-cols-2 gap-10 lg:gap-[120px]">
        <div
          v-for="(c, i) in topRow"
          :key="'top'+i"
          class="w-full max-w-[660px] mx-auto rounded-xl border border-white/90 bg-white/5 backdrop-blur-[2px] px-6 py-6 md:px-8 md:py-6 flex flex-col items-center gap-8"
        >
          <div class="h-11 w-11 rounded bg-[#EDECF6] flex items-center justify-center">
            <img :src="c.iconSrc" :alt="c.alt" class="h-6 w-6 object-contain" />
          </div>

          <div class="flex flex-col items-center gap-4 text-center max-w-[612px]">
            <h3 class="text-white text-[24px] leading-[29px] font-semibold">
              {{ c.title }}
            </h3>
            <p class="text-[#EDECF6] text-[18px] leading-[22px]">
              {{ c.desc }}
            </p>
          </div>
        </div>
      </div>

      <!-- row 2 -->
      <div class="mx-auto w-full max-w-[1440px] grid grid-cols-1 lg:grid-cols-2 gap-10 lg:gap-[120px]">
        <div
          v-for="(c, i) in bottomRow"
          :key="'bot'+i"
          class="w-full max-w-[660px] mx-auto rounded-xl border border-white/90 bg-white/5 backdrop-blur-[2px] px-6 py-6 md:px-8 md:py-6 flex flex-col items-center gap-8"
        >
          <div class="h-11 w-11 rounded bg-[#EDECF6] flex items-center justify-center">
            <img :src="c.iconSrc" :alt="c.alt" class="h-6 w-6 object-contain" />
          </div>

          <div class="flex flex-col items-center gap-4 text-center max-w-[612px]">
            <h3 class="text-white text-[24px] leading-[29px] font-semibold">
              {{ c.title }}
            </h3>
            <p class="text-[#EDECF6] text-[18px] leading-[22px]">
              {{ c.desc }}
            </p>
          </div>
        </div>
      </div>
    </div>

    <!-- Enterprise only -->
    <div class="relative z-20 w-full max-w-[1680px] mx-auto">
      <p class="text-center text-[#F9A71E] text-[32px] leading-[39px] font-semibold">
        Enterprise Only
      </p>
    </div>

    <!-- CTA bar -->
    <div
      class="relative z-20 w-full max-w-[1440px] mx-auto flex flex-col md:flex-row items-center justify-between gap-6 rounded-xl border border-[#EDECF6] bg-white/5 px-6 md:px-8 py-6"
    >
      <p class="text-[24px] leading-[29px] font-semibold text-[#F9A71E] text-center md:text-left">
        Be The First To Try Out Our New AI Features.
      </p>

      <form class="w-full md:w-auto flex items-center gap-4" @submit.prevent>
        <input
          type="email"
          placeholder="Enter email address"
          class="w-full md:w-[360px] h-[55px] rounded border border-[#EDECF6] bg-transparent px-4 text-white/80 placeholder-white/50 outline-none"
        />
        <button
          class="h-[42px] px-4 md:px-5 rounded bg-[#F9A71E] text-[#1A1C3D] text-[18px] font-semibold whitespace-nowrap"
        >
          Join AI Early Access
        </button>
      </form>
    </div>
  </section>
</template>
