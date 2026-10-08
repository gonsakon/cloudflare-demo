# 洧杰的第一ㄍ網站

Vue 3 + Vite 製作的繽紛積木網站，使用 **Cloudflare Pages** 與 GitHub 自動部署。

## 本機開發

使用 Node.js 24 LTS：

```sh
nvm use
npm ci
npm run dev
```

## Cloudflare Pages 自動部署

1. 登入 Cloudflare，進入 **Workers 和 Pages → 建立應用程式**。
2. 選擇頁面下方的 **前往 Pages**，再選擇匯入 Git 儲存庫。
3. 連接此 GitHub 儲存庫，使用以下設定：

- Production branch：`main`
- Build command：`npm run build`
- Framework preset：`Vue`（或選 None 並手動填入相同設定）
- Build output directory：`dist`
- Root directory：留空，使用儲存庫根目錄
- Node.js：由 `.nvmrc` 指定 `24`

4. 按 **儲存並部署**，完成後開啟 Cloudflare 提供的 `*.pages.dev` 網址。

連接成功後，推送到 `main` 就會觸發 Pages 建置與部署。
這個流程由 Pages 上傳 `dist`，不需要填寫 `npx wrangler deploy`，也不需要自行建立 API Token。

網站僅有前端，不使用 D1、R2 或後端服務。
