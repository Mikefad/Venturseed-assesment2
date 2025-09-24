<!-- PricingSection.vue -->
<template>
  <section class="pricing-section">
    <!-- MOBILE CARD (≤ md) -->
    <div
      class="md:hidden mx-auto w-[341px] h-[367px]
             rounded-[40px] bg-gradient-to-b from-[#42389E] to-[#0F1026]
             flex flex-col items-center justify-center gap-[10px] px-[155px] py-[34px]
             shadow-[0_0_10px_10px_rgba(0,0,0,0.05)]"
    >
      <div class="w-[313px] flex flex-col items-center gap-[24px]">
        <!-- Heading + paragraph -->
        <div class="w-[313px] flex flex-col items-center gap-2">
          <h2 class="w-full text-center text-white font-semibold text-[20px] leading-[24px]">
            Launch Features Confidently<br />
            With AI Driven Feature Flags
          </h2>
          <p class="w-[254px] mx-auto text-center text-[#FAFAFA] font-normal text-[18px] leading-[24px]">
            Start for free, scale as your team grows
          </p>
        </div>

        <!-- Buttons -->
        <div class="w-[313px] flex flex-col items-center gap-2">
          <!-- Primary -->
          <button
            class="w-[285px] h-[36px] rounded-[3.275px]
                   bg-[#F9A71E] flex items-center justify-center
                   px-[23.58px] py-[15.72px]"
          >
            <span
              class="font-bold text-[13.1px] leading-[15px]
                     bg-gradient-to-b from-[#42389E] to-[#0F1026] bg-clip-text text-transparent"
            >
              Get Started
            </span>
          </button>

          <!-- Outline -->
          <button
            class="w-[285px] h-[36px] rounded-[3.275px]
                   border border-[#F9A71E] flex items-center justify-center
                   px-[23.58px] py-[15.72px] text-[#F9A71E]"
          >
            <span class="font-bold text-[13.1px] leading-[15px]">Get Started</span>
          </button>
        </div>
      </div>
    </div>

    <!-- DESKTOP/TABLET (≥ md) — original hero card -->
    <div class="hero-card hidden md:flex">
      <div class="bg-pattern" aria-hidden="true"></div>
      <div class="hero-content">
        <h2 class="title">Pricing &amp; Plans</h2>
        <p class="subtitle">Start for free, scale as your team grows</p>
        <div class="actions">
          <button class="btn btn-primary">Start for $1/mo</button>
          <button class="btn btn-outline">Join AI Early Access</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// no script needed
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=DM+Sans:wght@700&family=Inter:wght@400;600&display=swap");

/* Container */
.pricing-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 120px 0 0;
  row-gap: 200px;
  width: 100%;
  max-width: 1920px;
  margin: 0 auto;
  min-height: 672.8px;
  height: auto;
  position: relative;
  box-sizing: border-box;
}

/* 🔧 Important: hide desktop card by default; show at md+ */
.hero-card { display: none; }
@media (min-width: 768px) {
  .hero-card { display: flex; }
}

/* Desktop card styles */
.hero-card {
  position: relative;
  width: 1384px;
  /* was 175px — too short for the buttons */
  height: 350px;              /* >= 214px so nothing is clipped */
  padding: 0 29px;
  justify-content: center;
  align-items: center;
  isolation: isolate;
  gap: 10px;
  background: linear-gradient(180deg, #42389E 0%, #0F1026 100%);
  box-shadow: 0 0 10px 10px rgba(0,0,0,0.05);
  border-radius: 12px;
  overflow: hidden;           /* or set to 'visible' if you prefer */
  margin: 0 auto;
}

.bg-pattern {
  position: absolute;
  left: 50%;
  top: 0;
  transform: translateX(-50%);
  width: 1185px;
  height: 375px;
  padding: 0 77px;
  opacity: 0.11;
  z-index: 1;
  outline: 0.536806px solid rgba(255, 255, 255, 0.5);
  outline-offset: -0.536806px;
  background-image:
    repeating-linear-gradient(to right, rgba(255,255,255,.5) 0, rgba(255,255,255,.5) .536806px, transparent .536806px, transparent 34.36px),
    repeating-linear-gradient(to bottom, rgba(255,255,255,.5) 0, rgba(255,255,255,.5) .536806px, transparent .536806px, transparent 34.36px);
  background-size: 34.36px 34.36px;
  background-position: 0 0, 0 0;
}
.hero-content {
  position: absolute;
  width: 649px;
  left: 50%;
  transform: translateX(-50%);
  top: 68.8px;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
}
.title {
  width: 100%;
  margin: 0;
  font-family: 'Inter', system-ui, -apple-system, Segoe UI, Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Apple Color Emoji', 'Segoe UI Emoji';
  font-weight: 600;
  font-size: 32px;
  line-height: 39px;
  text-align: center;
  color: #fff;
}
.subtitle {
  width: 100%;
  margin: 0;
  font-family: 'Inter', system-ui, -apple-system, Segoe UI, Roboto, 'Helvetica Neue', Arial, 'Noto Sans';
  font-weight: 400;
  font-size: 18px;
  line-height: 22px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: #fafafa;
  opacity: 0.9;
}
.actions {
  position: absolute;
  left: 0;
  top: 159px;
  width: 649px;
  height: 55px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 32px;
  z-index: 3;
}
.btn {
  height: 55px;
  min-width: 308.5px;
  padding: 12px 24px;
  border-radius: 5px;
  font-family: 'DM Sans', system-ui, -apple-system, Segoe UI, Roboto, 'Helvetica Neue', Arial, 'Noto Sans';
  font-weight: 700;
  font-size: 20px;
  line-height: 23px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  cursor: pointer;
  user-select: none;
  transition: transform 0.08s ease, box-shadow 0.2s ease, opacity 0.2s ease;
}
.btn:active { transform: translateY(1px); }
.btn-primary {
  background: #f9a71e;
  box-shadow: 0 4px 4px rgba(0,0,0,0.25);
  background-image:
    linear-gradient(180deg, #42389E 0%, #0F1026 100%),
    linear-gradient(#f9a71e, #f9a71e);
  background-clip: text, padding-box;
  -webkit-background-clip: text, padding-box;
  color: transparent;
  -webkit-text-fill-color: transparent;
}
.btn-outline {
  background: transparent;
  border: 1px solid #f9a71e;
  filter: drop-shadow(0 4px 4px rgba(0,0,0,0.25));
  color: #f9a71e;
}
.btn-primary:hover { opacity: .95; }
.btn-outline:hover { background: rgba(249,167,30,.08); }

/* existing responsive tweaks */
@media (max-width: 1400px) {
  .pricing-section { padding-top: 96px; row-gap: 160px; max-width: 100%; }
  .hero-card { width: min(92vw, 1384px); height: 400px; }
  .bg-pattern { width: calc(min(92vw, 1384px) - 58px); height: 100%; }
}
@media (max-width: 900px) {
  .pricing-section { padding-top: 72px; row-gap: 120px; }
  .actions { width: 100%; padding: 0 16px; gap: 16px; }
  .btn { min-width: 0; flex: 1 1 auto; }
}
</style>
