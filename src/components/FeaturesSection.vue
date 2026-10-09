<script setup>
const features = [
  {
    icon: '⚡',
    title: '极速构建',
    desc: '基于 Vite，毫秒级热更新，生产构建输出高度优化的静态资源。',
  },
  {
    icon: '🧩',
    title: '组件化开发',
    desc: 'Vue 3 组合式 API，页面拆分为独立组件，易于维护与扩展。',
  },
  {
    icon: '📱',
    title: '响应式布局',
    desc: '移动端到桌面端自适应，任何设备上都有出色的浏览体验。',
  },
  {
    icon: '🎨',
    title: '现代设计',
    desc: '深色主题、渐变色、柔和阴影与微交互，开箱即有高级感。',
  },
  {
    icon: '🚀',
    title: '一键部署',
    desc: '与 Vercel 无缝集成，推送代码即自动构建并全球分发。',
  },
  {
    icon: '🔍',
    title: 'SEO 友好',
    desc: '语义化 HTML 结构与完善的 meta 信息，利于搜索引擎收录。',
  },
]
</script>

<template>
  <section id="features" class="features">
    <div class="container">
      <h2 class="section-title">为什么选择 OnePage</h2>
      <p class="section-subtitle">为演示场景量身打造的每一项能力</p>
      <div class="grid">
        <div v-for="f in features" :key="f.title" class="card">
          <span class="icon">{{ f.icon }}</span>
          <h3>{{ f.title }}</h3>
          <p>{{ f.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.features {
  padding: 120px 0;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
}

.card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  padding: 32px;
  transition: transform 0.25s ease, border-color 0.25s ease;
}

.card:hover {
  transform: translateY(-4px);
  border-color: rgba(99, 102, 241, 0.5);
}

.icon {
  font-size: 2rem;
  display: block;
  margin-bottom: 16px;
}

h3 {
  font-size: 1.15rem;
  margin-bottom: 8px;
}

p {
  color: var(--color-text-dim);
  font-size: 0.95rem;
}
</style>
