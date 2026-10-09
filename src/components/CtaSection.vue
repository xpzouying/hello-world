<template>
  <section id="cta" class="cta">
    <div class="container cta-card">
      <h2>准备好开始了吗？</h2>
      <p>克隆这个模板，几分钟内部署你自己的 OnePage 站点。</p>
      <a
        class="btn btn-primary"
        href="https://vercel.com/new"
        target="_blank"
        rel="noopener"
      >
        在 Vercel 上部署 →
      </a>
    </div>
  </section>
</template>

<style scoped>
.cta {
  padding: 120px 0;
}

.cta-card {
  text-align: center;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: 24px;
  padding: 80px 32px;
  position: relative;
  overflow: hidden;
}

.cta-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(
    ellipse at top,
    rgba(99, 102, 241, 0.18),
    transparent 60%
  );
  pointer-events: none;
}

h2 {
  font-size: 2rem;
  margin-bottom: 12px;
  position: relative;
}

p {
  color: var(--color-text-dim);
  margin-bottom: 32px;
  position: relative;
}

.btn {
  position: relative;
}
</style>
