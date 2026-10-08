<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <div class="page">
    <header>
      <a class="brand" href="/" aria-label="Cloudflare Demo 首頁"><span class="brand-icon" aria-hidden="true">☁</span> CLOUDFLARE DEMO</a>
      <a class="source" href="https://github.com/gonsakon/cloudflare-demo">GitHub 原始碼 <span aria-hidden="true">↗</span></a>
    </header>

    <main>
      <p class="eyebrow"><span></span> A SMALL START, ON THE WEB</p>
      <h1>Hello,<br /><span>Cloudflare.</span></h1>
      <p class="intro">從一個想法，到一個網址。<br />這是我的第一個雲端示範網站。</p>
      <div class="interaction">
        <button type="button" @click="count++">打個招呼 <span aria-hidden="true">↗</span></button>
        <p role="status">{{ count ? `收到 ${count} 次招呼！互動正常。` : '點一下，試試網站的互動。' }}</p>
      </div>
    </main>

    <footer>
      <p>MADE WITH <strong>Vue 3 · Vite · Cloudflare</strong></p>
      <span>從這裡，開始下一個作品。</span>
    </footer>
  </div>
</template>
