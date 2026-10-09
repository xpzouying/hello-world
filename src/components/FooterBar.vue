<template>
  <footer class="footer">
    <div class="container footer-inner">
      <span>© {{ year }} OnePage. 仅供演示使用。</span>
      <span class="stack">Built with Vue 3 · Vite · Deployed on Vercel</span>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>

<style scoped>
.footer {
  border-top: 1px solid var(--color-border);
  padding: 32px 0;
}

.footer-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 8px;
  color: var(--color-text-dim);
  font-size: 0.9rem;
}
</style>
