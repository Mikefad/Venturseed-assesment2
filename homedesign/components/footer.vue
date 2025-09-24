<!-- File: IntelliToggleFooter.vue -->
<template>
  <footer class="footer">
    <div class="footer__container">
      <!-- Brand -->
      <div class="footer__brand">
        <div class="brand">
          <img :src="logoSrc" alt="" class="brand__logo" />
          <span class="brand__name">{{ brandName }}</span>
        </div>
        <p class="brand__blurb">
          {{ blurb }}
        </p>
        <a class="brand__icon" :href="brandIconHref" aria-label="GitHub">
          <span class="icon-circle"></span>
        </a>
      </div>

      <!-- Links -->
      <nav class="footer__links" aria-label="Footer">
        <div class="link-col">
          <h3>Resources</h3>
          <a v-for="(item, i) in resourcesLinks" :key="`res-${i}`" :href="item.href">
            {{ item.label }}
          </a>
        </div>
        <div class="link-col">
          <h3>Company</h3>
          <a v-for="(item, i) in companyLinks" :key="`cmp-${i}`" :href="item.href">
            {{ item.label }}
          </a>
        </div>
      </nav>

      <!-- Newsletter -->
      <div class="footer__cta">
        <h3>Subscribe to Newsletter</h3>
        <form class="subscribe" @submit.prevent="onSubmit" novalidate>
          <label class="sr-only" for="email">Email address</label>
          <input
            id="email"
            v-model.trim="email"
            type="email"
            inputmode="email"
            autocomplete="email"
            placeholder="Enter email address"
            :aria-invalid="error ? 'true' : 'false'"
            :aria-describedby="error ? 'email-error' : undefined"
            required
          />
          <button type="submit">Subscribe</button>
        </form>
        <p v-if="error" id="email-error" class="error">{{ error }}</p>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { ref } from 'vue'

type LinkItem = { label: string; href: string }

const props = withDefaults(defineProps<{
  logoSrc?: string
  brandName?: string
  blurb?: string
  brandIconHref?: string
  resourcesLinks?: LinkItem[]
  companyLinks?: LinkItem[]
}>(), {
  logoSrc: '/footerlogo.png',
  brandName: 'IntelliToggle',
  blurb:
    'IntelliToggle is built by AORTEM, a company focused on powering scalable, multi-platform developer tools.',
  brandIconHref: '#',
  resourcesLinks: () => ([
    { label: 'Why IntelliToggle is different', href: '#' },
    { label: 'Customer Support', href: '#' },
    { label: 'Terms & conditions', href: '#' },
    { label: 'Privacy Policy', href: '#' },
  ]),
  companyLinks: () => ([
    { label: 'Pricing', href: '#' },
    { label: 'Documentation', href: '#' },
    { label: 'About Us', href: '#' },
  ]),
})

const emit = defineEmits<{
  (e: 'subscribe', email: string): void
}>()

const email = ref('')
const error = ref<string | null>(null)

function onSubmit() {
  // basic validation
  const valid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email.value)
  if (!valid) {
    error.value = 'Please enter a valid email address.'
    return
  }
  error.value = null
  emit('subscribe', email.value)
  // Optional: clear after submit
  email.value = ''
}
</script>

<style scoped>
/* ========= Footer ========= */
.footer {
  background: #ECEBF5;             /* matches your design color */
  padding: 100px 24px;             /* mobile-friendly side padding */
  width: 100%;
  box-sizing: border-box;          /* prevent padding from widening the element */
}

.footer__container {
  max-width: 1200px;               /* centered content; adjust if your grid differs */
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1.3fr 1fr 1fr; /* brand | resources | company/cta */
  gap: 56px;
  align-items: start;
}

/* Brand */
.footer__brand .brand {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 16px;
}

.brand__logo {
  width: 48px;
  height: 48px;
  object-fit: contain;
}

.brand__name {
  font-weight: 700;
  font-size: 20px;
}

.brand__blurb {
  color: #5a5a66;
  line-height: 1.6;
  margin: 12px 0 16px;
  max-width: 520px;
}

.brand__icon .icon-circle {
  display: inline-block;
  width: 28px;
  height: 28px;
  border-radius: 50%;
  background: #2f2f3a;
}

/* Link columns */
.footer__links {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px;
}

.link-col h3 {
  font-size: 16px;
  font-weight: 600;
  margin: 0 0 12px;
  color: #1f1f29;
}

.link-col a {
  display: block;
  text-decoration: none;
  color: #1f1f29;
  opacity: 0.85;
  padding: 8px 0;
}

.link-col a:hover,
.link-col a:focus {
  opacity: 1;
  text-decoration: underline;
}

/* Newsletter */
.footer__cta h3 {
  margin: 0 0 12px;
  font-size: 16px;
  font-weight: 600;
}

.subscribe {
  display: flex;
  align-items: stretch;
  gap: 0;
  background: white;
  border-radius: 8px;
  overflow: hidden;
  max-width: 520px;
}

.subscribe input {
  flex: 1 1 auto;
  border: 0;
  padding: 14px 16px;
  font-size: 14px;
  min-width: 0; /* prevents overflow in flex container */
}

.subscribe input:focus {
  outline: 2px solid #c7c6d6;
  outline-offset: -2px;
}

.subscribe button {
  border: 0;
  padding: 0 20px;
  font-weight: 600;
  cursor: pointer;
  background: #F59E0B;   /* orange button from screenshot */
  color: #111;
}

.subscribe button:hover {
  filter: brightness(0.95);
}

.error {
  margin-top: 8px;
  font-size: 12px;
  color: #b00020;
}

/* A11y helper for the label */
.sr-only {
  position: absolute !important;
  height: 1px;
  width: 1px;
  overflow: hidden;
  clip: rect(1px, 1px, 1px, 1px);
  white-space: nowrap;
}

/* ======= Responsive ======= */
@media (max-width: 1024px) {
  .footer__container {
    grid-template-columns: 1fr 1fr; /* stack CTA under links */
  }
  .footer__cta {
    grid-column: 1 / -1;
  }
}

@media (max-width: 720px) {
  .footer {
    padding: 64px 20px;
  }
  .footer__container {
    grid-template-columns: 1fr; /* full stack */
    gap: 36px;
  }
  .footer__links {
    grid-template-columns: 1fr; /* stack link groups */
  }
  .subscribe {
    max-width: 100%;
  }
}
</style>
