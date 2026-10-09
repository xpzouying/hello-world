<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const stats = [
  { value: 100, suffix: '分', label: 'Lighthouse 性能' },
  { value: 50, suffix: 'ms', label: '全球平均延迟' },
  { value: 99.9, suffix: '%', label: '可用性保障', decimals: 1 },
  { value: 1, suffix: '分钟', label: '从推送到上线' },
]

const display = ref(stats.map(() => 0))
const sectionEl = ref(null)
let observer = null
let animated = false

function animate() {
  const duration = 1400
  const start = performance.now()
  const tick = (now) => {
    const p = Math.min((now - start) / duration, 1)
    const eased = 1 - Math.pow(1 - p, 3)
    display.value = stats.map((s) => +(s.value * eased).toFixed(s.decimals ?? 0))
    if (p < 1) requestAnimationFrame(tick)
  }
  requestAnimationFrame(tick)
}

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting && !animated) {
        animated = true
        animate()
        observer.disconnect()
      }
    },
    { threshold: 0.4 }
  )
  observer.observe(sectionEl.value)
})

onUnmounted(() => observer?.disconnect())
</script>

<template>
  <section id="showcase" ref="sectionEl" class="showcase">
    <div class="container">
      <h2 class="section-title">用数据说话</h2>
      <p class="section-subtitle">部署在现代边缘网络上的真实表现</p>
      <div class="stats">
        <div v-for="(s, i) in stats" :key="s.label" class="stat">
          <span class="value">{{ display[i] }}<em>{{ s.suffix }}</em></span>
          <span class="label">{{ s.label }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.showcase {
  padding: 120px 0;
  background: var(--color-surface);
  border-top: 1px solid var(--color-border);
  border-bottom: 1px solid var(--color-border);
}

.stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 32px;
  text-align: center;
}

.value {
  display: block;
  font-size: 3rem;
  font-weight: 800;
  background: var(--gradient);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.value em {
  font-style: normal;
  font-size: 1.4rem;
  margin-left: 2px;
}

.label {
  color: var(--color-text-dim);
  font-size: 0.95rem;
}
</style>
