<template>
  <section id="home" class="hero">
    <div class="hero-glow" aria-hidden="true"></div>
    <div class="container hero-inner">
      <span class="badge">✨ Vue 3 + Vite 驱动</span>
      <h1>
        一个页面，<br />
        <span class="gradient-text">讲好你的产品故事</span>
      </h1>
      <p class="lead">
        OnePage 是一个现代化的单页演示站点模板。响应式布局、流畅动效、
        开箱即部署 —— 把精力留给内容本身。
      </p>
      <div class="actions">
        <a href="#cta" class="btn btn-primary">立即体验</a>
        <a href="#features" class="btn btn-ghost">了解特性 ↓</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.hero-glow {
  position: absolute;
  top: -20%;
  left: 50%;
  transform: translateX(-50%);
  width: 720px;
  height: 720px;
  background: radial-gradient(
    circle,
    rgba(99, 102, 241, 0.28),
    rgba(168, 85, 247, 0.12) 45%,
    transparent 70%
  );
  pointer-events: none;
}

.hero-inner {
  position: relative;
  text-align: center;
  padding-top: 96px;
  padding-bottom: 64px;
}

.badge {
  display: inline-block;
  padding: 6px 16px;
  border-radius: 999px;
  border: 1px solid var(--color-border);
  background: var(--color-surface);
  color: var(--color-text-dim);
  font-size: 0.85rem;
  margin-bottom: 28px;
}

h1 {
  font-size: clamp(2.4rem, 6vw, 4rem);
  font-weight: 800;
  line-height: 1.15;
  letter-spacing: -0.02em;
  margin-bottom: 24px;
}

.gradient-text {
  background: var(--gradient);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.lead {
  max-width: 560px;
  margin: 0 auto 40px;
  color: var(--color-text-dim);
  font-size: 1.1rem;
}

.actions {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
}
</style>
