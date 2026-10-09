<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const links = [
  { href: '#home', label: '首页' },
  { href: '#features', label: '特性' },
  { href: '#showcase', label: '数据' },
  { href: '#cta', label: '开始' },
]

const scrolled = ref(false)
const onScroll = () => {
  scrolled.value = window.scrollY > 24
}
onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<template>
  <header class="nav" :class="{ scrolled }">
    <div class="container nav-inner">
      <a href="#home" class="logo">
        <span class="logo-mark">O</span>
        OnePage
      </a>
      <nav class="links">
        <a v-for="link in links" :key="link.href" :href="link.href">
          {{ link.label }}
        </a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  transition: background 0.3s ease, border-color 0.3s ease;
  border-bottom: 1px solid transparent;
}

.nav.scrolled {
  background: rgba(11, 13, 23, 0.82);
  backdrop-filter: blur(12px);
  border-bottom-color: var(--color-border);
}

.nav-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 64px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 1.15rem;
  font-weight: 700;
}

.logo-mark {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 30px;
  height: 30px;
  border-radius: 8px;
  background: var(--gradient);
  font-size: 0.95rem;
}

.links {
  display: flex;
  gap: 32px;
}

.links a {
  color: var(--color-text-dim);
  font-size: 0.95rem;
  transition: color 0.2s ease;
}

.links a:hover {
  color: var(--color-text);
}

@media (max-width: 560px) {
  .links {
    gap: 18px;
  }
}
</style>
