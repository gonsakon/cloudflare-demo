<script setup>
import { onUnmounted, ref } from 'vue'

const count = ref(0)
const celebrating = ref(false)
let celebrationTimer

function sayHello() {
  count.value++
  celebrating.value = true
  clearTimeout(celebrationTimer)
  celebrationTimer = setTimeout(() => { celebrating.value = false }, 900)
}

onUnmounted(() => clearTimeout(celebrationTimer))
</script>

<template>
  <div class="page" :class="{ celebrating }">
    <header class="site-header">
      <a class="brand" href="/" aria-label="洧杰的第一ㄍ網站 首頁">
        <span class="mini-block" aria-hidden="true"><i></i><i></i></span>
        洧杰的創意基地<span class="brand-dot">●</span>
      </a>
      <a class="source" href="https://github.com/gonsakon/cloudflare-demo">看看原始碼 <span aria-hidden="true">↗</span></a>
    </header>

    <main>
      <section class="slide" aria-labelledby="site-title">
        <div class="slide-bar">
          <span class="window-dots" aria-hidden="true"><i></i><i></i><i></i></span>
          <span>小小想法，大大世界</span><span class="slide-number">NO. 001</span>
        </div>
        <div class="hero">
          <div class="hero-copy">
            <p class="eyebrow"><span aria-hidden="true">✦</span> 嗨，歡迎來玩！</p>
            <h1 id="site-title">洧杰的<br /><span class="title-highlight">第一ㄍ</span>網站</h1>
            <p class="intro">把一點好奇、一點創意，<br />拼成一個可以逛的地方。</p>
            <div class="interaction">
              <button class="hello-button" type="button" @click="sayHello">跟洧杰打招呼 <span aria-hidden="true">↗</span></button>
              <p class="hello-status" role="status">{{ count ? `耶！收到 ${count} 次招呼，開心加倍！` : '點一下，讓積木們開心一下。' }}</p>
            </div>
          </div>
          <div class="playground" aria-hidden="true">
            <span class="art-label">IDEAS AT PLAY</span>
            <span class="hello-sticker">HELLO<span>你好呀！</span></span>
            <span class="spark spark-one">✦</span><span class="spark spark-two">✳</span><span class="spark spark-three">✦</span>
            <div class="block-scene">
              <div class="floor-shadow"></div>
              <div class="brick brick-mint"><div class="studs"><i></i><i></i><i></i><i></i></div><span class="brick-mark">LET'S BUILD!</span></div>
              <div class="brick brick-pink"><div class="studs"><i></i><i></i></div><div class="face"><span class="eye"></span><span class="eye"></span><span class="smile"></span></div><span class="cheek"></span></div>
              <div class="brick brick-yellow"><div class="studs"><i></i><i></i><i></i></div><div class="face"><span class="eye"></span><span class="eye"></span><span class="smile"></span></div><span class="cheek"></span></div>
              <div class="brick brick-blue"><div class="studs"><i></i><i></i></div><span class="little-star">✦</span></div>
            </div>
            <div class="art-note"><span>↖</span> 好玩的事情，從一小塊開始。</div>
            <div class="confetti"><i v-for="n in 12" :key="n" :style="{ '--i': n }"></i></div>
          </div>
        </div>
        <div class="slide-bottom"><span><b>●</b> 第一個作品，正式登場！</span><span>用好奇心，把世界拼大一點 <span aria-hidden="true">↗</span></span></div>
      </section>
      <div class="idea-cards" aria-label="網站的小小配方">
        <article class="idea-card card-yellow"><span class="card-icon" aria-hidden="true">✳</span><div><p>01 / 靈感</p><h2>從「試試看」開始</h2></div><span class="card-arrow" aria-hidden="true">↗</span></article>
        <article class="idea-card card-pink"><span class="card-icon" aria-hidden="true">♥</span><div><p>02 / 創作</p><h2>認真玩，也好好做</h2></div><span class="card-arrow" aria-hidden="true">↗</span></article>
        <article class="idea-card card-mint"><span class="card-icon" aria-hidden="true">✦</span><div><p>03 / 下一步</p><h2>還有好多好多可能</h2></div><span class="card-arrow" aria-hidden="true">↗</span></article>
      </div>
    </main>

    <footer>
      <span>洧杰的第一ㄍ網站 <span aria-hidden="true">✦</span></span>
      <span>MADE WITH CURIOSITY & A LITTLE BIT OF MAGIC.</span>
    </footer>
  </div>
</template>
