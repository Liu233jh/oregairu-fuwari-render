# oregairu-fuwari · Render 部署配置

这个仓库**只存放 Render Blueprint**，实际部署的代码仍然是原仓库 `Liu233jh/oregairu-fuwari`。原仓库与 GitHub Pages 都不会被改动。

## 一键部署

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/Liu233jh/oregairu-fuwari-render)

部署完成后访问：`https://oregairu-fuwari.onrender.com/oregairu-fuwari/`

## 配置说明

- 类型：Static Site（免费、全球 CDN、不休眠）
- 构建：`pnpm install --no-frozen-lockfile && pnpm build`
- 发布目录：`dist/client`
- Rewrite：`/oregairu-fuwari/*` → `/*`

## 已知限制

- 根路径 `/` 会 404（Render 不允许对域名根应用 rewrite）
- sitemap / canonical 仍指向 `liu233jh.github.io`
- 原因：原仓库 `astro.config.mjs` 中 `base` 与 `site` 均为硬编码，本次约定不改代码
