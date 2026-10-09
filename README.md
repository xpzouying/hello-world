# OnePage · 演示首页

一个基于 **Vue 3 + Vite** 的现代化单页（OnePage）演示站点，Node 20，可一键部署到 Vercel。

## 本地开发

```bash
# 使用 Node 20（如已安装 nvm）
nvm use

npm install
npm run dev
```

打开 http://localhost:5173 预览。

## 构建

```bash
npm run build    # 产物输出到 dist/
npm run preview  # 本地预览构建产物
```

## 部署到 Vercel

方式一：在 [Vercel](https://vercel.com/new) 导入本仓库，Vercel 会自动识别 Vite 项目（Build Command: `vite build`，Output: `dist`），无需额外配置。

方式二：使用 Vercel CLI：

```bash
npm i -g vercel
vercel
```

项目通过 `.nvmrc` 和 `package.json` 的 `engines` 字段锁定 Node 20。

## 页面结构

- `NavBar` — 吸顶导航，滚动时毛玻璃效果
- `HeroSection` — 首屏大标题 + 渐变光晕
- `FeaturesSection` — 特性卡片网格
- `ShowcaseSection` — 滚动进入视口时的数字动画
- `CtaSection` — 行动召唤卡片
- `FooterBar` — 页脚
