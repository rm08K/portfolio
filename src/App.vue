<script setup lang="ts">
import { ref } from 'vue'
import BaseModal from './components/BaseModal.vue'
import SelfPortrait from './components/SelfPortrait.vue'

const activeWork = ref<number | null>(null)
const assetPath = (path: string) => `${import.meta.env.BASE_URL}${path}`

const works = [
  {
    title: 'デジタルハリウッド大学のWebデザイン・開発を知るサイト',
    thumbnail: assetPath('images/website/website_small_1.jpg'),
    image: assetPath('images/website/website_1.png'),
    period: '2週間程度',
    tools: 'Adobe XD, Photoshop, Visual Studio Code, HTML, CSS, JavaScript',
    description: '大学のWebサイトをリデザインする課題の一環で制作しました。画像は全て元々用意されていたものを使用しています。動きに集中して制作したので、アニメーションが少し強めに入っています。レスポンシブデザイン標準です。（リンクは機能しません）',
    links: [
      ['デジタルハリウッド大学のWebデザイン・開発の学習を知るサイト', 'https://rm08k.github.io/WebsiteExpressionExercisesAppliedA/'],
      ['GitHub', 'https://github.com/rm08K/WebsiteExpressionExercisesAppliedA'],
    ],
  },
  {
    title: 'Static to Nuxt',
    thumbnail: assetPath('images/website/website_small_2.jpg'),
    image: assetPath('images/website/website_2.png'),
    period: '2週間程度',
    tools: 'Photoshop, Visual Studio Code, Nuxt.js, Vue.js, HTML, CSS, JavaScript',
    description: '元々すでにデザインされたサイトをコーディングする課題にてHTMLで制作したものを、NuxtでSPAに書き換えたものです。このポートフォリオと同じくNuxtのFull Static Generationを使用してコーディングしています。SPAなのでシームレスに別のページへ遷移します。',
    links: [
      ['BMW Fan!!!!!!', 'https://rm08k.github.io/StaticToNuxt/'],
      ['GitHub', 'https://github.com/rm08K/StaticToNuxt'],
    ],
  },
  {
    title: '南国料理人っぽいことをしてみた',
    thumbnail: assetPath('images/website/youtube1.jpg'),
    period: '1ヶ月弱',
    tools: 'iPhone, Adobe Premiere Pro, Photoshop',
    description: 'フードロス問題を解決する提案の動画を作成する課題の一環にて制作しました。制限時間が1分と短いため、それを利用してわちゃわちゃとした動画になっています。企画・キャストはチームのメンバーが、撮影・編集は自分が行っています。',
    links: [['A1_DH2018後期_特攻野郎Dチーム', 'https://youtu.be/lq4DFjYkqao']],
    video: 'https://www.youtube.com/embed/lq4DFjYkqao',
  },
]
</script>

<template>
  <main>
    <section class="hero">
      <SelfPortrait />
      <h1>RyosuKe</h1>
    </section>

    <section class="section about">
      <h2>about</h2>
      <p>
        1999年生まれ。<br />
        パソコンが好きで小さい頃から色々触ってきました。<br />
        現在はWebのコーディングとデザインを勉強しています。<br />
        Adobe製品全般を扱うことができるので、動画の編集もやったりしてます。
      </p>
    </section>

    <section class="section works">
      <h2>works</h2>
      <div class="work-grid">
        <button v-for="(work, index) in works" :key="work.title" class="work-card" type="button" @click="activeWork = index">
          <img :src="work.thumbnail" :alt="`${work.title} のサムネイル`" />
        </button>
      </div>
    </section>

    <BaseModal v-if="activeWork !== null" @close="activeWork = null">
      <template v-if="works[activeWork]">
        <h3>{{ works[activeWork].title }}</h3>
        <div v-if="works[activeWork].video" class="video-wrapper">
          <iframe
            :src="works[activeWork].video"
            :title="works[activeWork].title"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          />
        </div>
        <img v-else class="work-image" :src="works[activeWork].image" :alt="works[activeWork].title" />
        <dl>
          <dt>制作期間</dt>
          <dd>{{ works[activeWork].period }}</dd>
          <dt>使用した技術・ツール</dt>
          <dd>{{ works[activeWork].tools }}</dd>
          <dt>説明</dt>
          <dd>{{ works[activeWork].description }}</dd>
          <dt>サイトリンク</dt>
          <dd>
            <a v-for="([label, url]) in works[activeWork].links" :key="url" :href="url" target="_blank" rel="noopener noreferrer">
              {{ label }}
            </a>
          </dd>
        </dl>
        <button class="close-button" type="button" @click="activeWork = null">閉じる</button>
      </template>
    </BaseModal>
  </main>
</template>

<style>
:root {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  color: #35495e;
}

body {
  margin: 0;
}

.hero,
.section {
  display: flex;
  flex-flow: column;
  align-items: center;
  justify-content: center;
  min-block-size: 100vh;
  padding: 2rem;
  box-sizing: border-box;
  text-align: center;
}

.hero h1 {
  margin: 20px 0 0;
  font-size: clamp(3.5rem, 10vw, 5rem);
  font-weight: 300;
  letter-spacing: 1px;
}

.about {
  background: #eee;
}

.section h2 {
  font-size: 2rem;
}

.section p {
  line-height: 1.8;
}

.works {
  background: #fff;
}

.work-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}

.work-card {
  display: block;
  min-inline-size: 280px;
  max-inline-size: 360px;
  padding: 0;
  overflow: hidden;
  cursor: pointer;
  border: 0;
  background: none;
}

.work-card img,
.work-image {
  display: block;
  inline-size: 100%;
}

.video-wrapper {
  position: relative;
  padding-block-start: 56.25%;
}

.video-wrapper iframe {
  position: absolute;
  inset: 0;
  inline-size: 100%;
  block-size: 100%;
  border: 0;
}

dl {
  text-align: left;
}

dt {
  margin-block: 1.25rem 0.3rem;
  font-size: 1.2rem;
}

dd {
  margin-inline-start: 0;
  line-height: 1.6;
}

dd a {
  display: block;
}

.close-button {
  padding: 0.7rem 1.1rem;
  cursor: pointer;
}

@media (max-width: 600px) {
  .self-port {
    max-inline-size: 100%;
    block-size: auto;
  }
}
</style>
