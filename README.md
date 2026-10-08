# Cloudflare Demo

依照 [六角學院 Cloudflare 教材](https://www.casper.tw/hex-in-house-training/#/internal-training/cloudflare) 建立的 Vue 3 + Vite 靜態示範網站。

## 本機開發

使用 Node.js 24 LTS：

```sh
nvm use
npm ci
npm run dev
```

## Cloudflare 自動部署

在 Workers 和 Pages 建立應用程式，連接此 GitHub 儲存庫：

- Production branch：`main`
- Build command：`npm run build`
- Deploy command：`npx wrangler deploy`
- Root directory：`/`

`wrangler.jsonc` 將建置後的 `dist` 目錄設定為靜態資產。連接成功後，推送到 `main` 就會觸發部署。

網站僅有前端，不使用 D1、R2 或後端服務。
