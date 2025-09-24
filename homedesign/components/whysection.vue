<script setup lang="ts">
type Feature = { icon: string; title: string; desc: string }

const features: Feature[] = [
  { icon: "🎚️", title: "Safer, faster rollouts", desc: "Control feature releases in minutes, not weeks without risking production stability." },
  { icon: "🪂", title: "Confidence to ship", desc: "“Flip, target, and roll back. Engineers ship more often knowing they can undo mistakes." },
  { icon: "🤖", title: "Future-ready with AI delivery", desc: "Built for Dart workflows and already prepared for AI-powered rollout automation tomorrow." },
]

// NEW: map emoji → icon file in /public/icons
const iconMap: Record<string, string> = {
  "🎚️": "/ant-design_control-filled.png",
  "🪂": "/eos-icons_code-deploy.png",
  "🤖": "/eos-icons_ai-operator.png",
}
</script>

<template>
  <!-- Why Teams Use IntelliToggle -->
  <section class="hidden md:block w-full bg-white py-28 px-6 md:px-10">
    <div class="mx-auto max-w-screen-2xl flex flex-col items-center gap-12">
      <h2 class="text-[40px] leading-[54px] font-bold text-center bg-gradient-to-b from-[#42389E] to-[#0F1026] bg-clip-text text-transparent">
        Why Teams Use IntelliToggle
      </h2>

      <div class="w-full flex flex-col items-center gap-8">
        <div class="w-full flex flex-col lg:flex-row justify-center items-start gap-10 lg:gap-24">
          <div v-for="(f, i) in features" :key="i" class="w-full max-w-[402px] flex flex-col gap-12">
            <div class="w-[129px] h-[118px] rounded-lg border border-[#342d7e] bg-[#EDECF6] flex items-center justify-center text-4xl">
              <NuxtImg
                v-if="iconMap[f.icon]"
                :src="iconMap[f.icon]"
                :alt="f.title"
                class="h-12 w-12 object-contain"
                draggable="false"
                loading="lazy"
              />
              <span v-else aria-hidden="true">{{ f.icon }}</span>
            </div>

            <div class="flex flex-col gap-2">
              <h3 class="text-[24px] leading-[29px] font-semibold text-[#1A1C3D]">{{ f.title }}</h3>
              <p class="text-[18px] leading-[22px] text-[#5F5F60]">{{ f.desc }}</p>
            </div>
          </div>
        </div>

        <div class="w-full max-w-[1394px] box-border flex items-center justify-between gap-8 rounded-xl bg-[#EDECF6] shadow-[0_0_10px_10px_rgba(0,0,0,0.05)] px-8 py-4">
          <div class="mx-auto flex-1 flex items-center gap-4 min-w-0" title="Heading and supporting text">
            <p class="text-[24px] leading-[29px] font-semibold text-[#0E121B] truncate">
              Read a 2-min case note: How a sample Flutter app shipped faster with IntelliToggle
            </p>
          </div>
          <button class="shrink-0 inline-flex items-center justify-center px-6 py-3 rounded-lg bg-[#F9A71E] shadow-[0_0_10px_10px_rgba(0,0,0,0.05)]">
            <span class="text-[18px] leading-[22px] font-semibold bg-gradient-to-b from-[#42389E] to-[#0F1026] bg-clip-text text-transparent">Read Now</span>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>
