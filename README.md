# oregairu-fuwari · Render 部署配置

这个仓库**只存放 Render Blueprint**，实际部署的代码仍然是原仓库 `Liu233jh/oregairu-fuwari`。原仓库与 GitHub Pages 都不会被改动。

## 访问地址

- 推荐：`https://oregairu-fuwari.onrender.com/oregairu-fuwari/`
- 根路径也可用：`https://oregairu-fuwari.onrender.com/`

## 配置说明

- 类型：Static Site（免费、全球 CDN、不休眠）
- 发布目录：`dist/client`
- 构建命令做了两件事：
  1. `pnpm install --no-frozen-lockfile && pnpm build`
  2. 构建完成后把整站复制到 `dist/client/oregairu-fuwari/`

第二步是为了兼容原仓库 `astro.config.mjs` 里写死的 `base = "/oregairu-fuwari/"`：复制后 `_astro`、`live2d/runtime`、`pagefind` 等资源路径物理存在，不依赖 Render 的 rewrite 规则（实测 rewrite 对多级资源路径会漏）。

## 已知限制

- sitemap / canonical 仍指向 `liu233jh.github.io`
- 部署产物中站点存两份（根路径 + 前缀路径）；带宽按实际请求计算，不影响免费额度
- 以上都源于「不修改原仓库代码」的约定
