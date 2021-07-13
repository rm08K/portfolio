<template>
  <div class="container">
    <div class="topView">
      <Self />
      <h1 class="title">
        RyosuKe
      </h1>
    </div>
    <div class="secondView">
      <h2 class="subTitle">
        about
      </h2>
      <p>
        1999年生まれ。
        <br>パソコンが好きで小さい頃から色々触ってきました。
        <br>現在はWebのコーディングとデザインを勉強しています。
        <br>Adobe製品全般を扱うことができるので、動画の編集もやったりしてます。
      </p>
    </div>
    <div class="secondView white">
      <h2 class="subTitle">
        works
      </h2>
      <div class="flexboxContainer">
        <div class="flexboxContainer-contents">
          <div>
            <img class="flexboxContainer-contents_img " src="images/website/website_small_1.jpg" alt="" @click="openModal1">
            <Modal v-if="modalFlag1" @close-modal="closeModal1">
              <div class="modalbox">
                <h3 class="modalbox-title">
                  デジタルハリウッド大学のWebデザイン・開発を知るサイト
                </h3>
                <img class="modalbox-img" src="images/website/website_1.png" alt="">
                <dl class="modalbox-description">
                  <dt>制作期間</dt>
                  <dd>2週間程度</dd>
                  <dt>使用した技術・ツール</dt>
                  <dd>Adobe XD, Photoshop, Visual Studio Code, HTML, CSS, Javascript</dd>
                  <dt>説明</dt>
                  <dd>
                    大学のWebサイトをリデザインする課題の一環で制作しました。<br>
                    画像は全て元々用意されていたものを使用しています。<br>
                    動きに集中して制作したので、アニメーションが少し強めに入っています。<br>
                    レスポンシブデザイン標準です。（リンクは機能しません）
                  </dd>
                  <dt>サイトリンク</dt>
                  <dd>
                    <a href="https://rm08k.github.io/WebsiteExpressionExercisesAppliedA/" target="_blank" rel="noopener noreferrer">デジタルハリウッド大学のWebデザイン・開発の学習を知るサイト</a><br>
                    <a href="https://github.com/rm08K/WebsiteExpressionExercisesAppliedA" target="_blank" rel="noopener noreferrer">Github</a>
                  </dd>
                </dl>
              </div>
              <button class="flexboxContainer-contents_button" @click="closeModal1">
                閉じる
              </button>
            </Modal>
          </div>
        </div>
        <div class="flexboxContainer-contents">
          <div>
            <img class="flexboxContainer-contents_img " src="images/website/website_small_2.jpg" alt="" @click="openModal2">
            <Modal v-if="modalFlag2" @close-modal="closeModal2">
              <div class="modalbox">
                <h3 class="modalbox-title">
                  Static to Nuxt
                </h3>
                <img class="modalbox-img" src="images/website/website_2.png" alt="">
                <dl class="modalbox-description">
                  <dt>制作期間</dt>
                  <dd>2週間程度</dd>
                  <dt>使用した技術・ツール</dt>
                  <dd>Photoshop, Visual Studio Code, Nuxt.js, Vue.js, HTML, CSS, Javascript</dd>
                  <dt>説明</dt>
                  <dd>
                    元々すでにデザインされたサイトをコーディングする課題にてHTMLで制作したものを、NuxtでSPAに書き換えたものです。<br>
                    このポートフォリオと同じくNuxtのFull Static Generationを使用してコーディングしています。<br>
                    SPAなのでシームレスに別のページへ遷移します。
                  </dd>
                  <dt>サイトリンク</dt>
                  <dd>
                    <a href="https://rm08k.github.io/StaticToNuxt/" target="_blank" rel="noopener noreferrer">BMW Fan!!!!!!</a><br>
                    <a href="https://github.com/rm08K/StaticToNuxt" target="_blank" rel="noopener noreferrer">Github</a>
                  </dd>
                </dl>
              </div>
              <button class="flexboxContainer-contents_button" @click="closeModal2">
                閉じる
              </button>
            </Modal>
          </div>
        </div>
        <div class="flexboxContainer-contents">
          <div>
            <img class="flexboxContainer-contents_img " src="images/website/youtube1.jpg" alt="" @click="openModal3">
            <Modal v-if="modalFlag3" @close-modal="closeModal3">
              <div class="modalbox">
                <h3 class="modalbox-title">
                  南国料理人っぽいことをしてみた
                </h3>
                <div class="modalbox-wrapper">
                  <iframe
                    class="modalbox-iframe"
                    src="https://www.youtube.com/embed/lq4DFjYkqao"
                    title="YouTube video player"
                    frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen
                  >
                    <!-- ここ謎 -->
                  </iframe>
                </div>
                <dl class="modalbox-description">
                  <dt>制作期間</dt>
                  <dd>1ヶ月弱</dd>
                  <dt>使用した技術・ツール</dt>
                  <dd>iPhone, Adobe Premiere Pro, Photoshop, </dd>
                  <dt>説明</dt>
                  <dd>
                    フードロス問題を解決する提案の動画を作成する課題の一環にて制作しました。<br>
                    制限時間が1分と短いため、それを利用してわちゃわちゃとした動画になっています。<br>
                    企画・キャストはチームのメンバーが、撮影・編集は自分が行っています。
                  </dd>
                  <dt>サイトリンク</dt>
                  <dd>
                    <a href="https://youtu.be/lq4DFjYkqao" target="_blank" rel="noopener noreferrer">A1_DH2018後期_特攻野郎Dチーム</a>
                  </dd>
                </dl>
              </div>
              <button class="flexboxContainer-contents_button" @click="closeModal3">
                閉じる
              </button>
            </Modal>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// export default {}
import Vue from 'vue'
import Modal from '~/components/Modal.vue'

export default Vue.extend({
  components: {
    Modal
  },
  data() {
    return {
      modalFlag1: false,
      modalFlag2: false,
      modalFlag3: false
    }
  },
  methods: {
    openModal1() {
      this.modalFlag1 = true
    },
    closeModal1() {
      this.modalFlag1 = false
    },
    openModal2() {
      this.modalFlag2 = true
    },
    closeModal2() {
      this.modalFlag2 = false
    },
    openModal3() {
      this.modalFlag3 = true
    },
    closeModal3() {
      this.modalFlag3 = false
    }
  }
})
// ここほんとにひどいw
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  min-height: 100vh;
  text-align: center;
}

.topView {
  block-size: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: inline-block;
  font-weight: 300;
  font-size: 80px;
  color: #35495e;
  letter-spacing: 1px;
  margin-top: 20px;
}

.secondView {
  min-block-size: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column;
  background-color: #eee;
}

.white {
  background-color: #fff;
}

.flexboxContainer {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  &-contents {
    min-inline-size: 300px;
    max-inline-size: 30vw ;
    margin: 10px;
    &_img {
      inline-size: 100%;
      cursor: pointer;
    }
  }
}

.modalbox {
  overflow: scroll;
  inline-size: 100%;
  &-title {
    margin-top: 0;
  }
  &-img {
    inline-size: 100%;
  }
  &-p {
    text-align: left;
  }
  &-description {
    text-align: left;
    & dt {
      font-size: 1.2rem;
      margin-bottom: 5px;
    }
    & dd {
      margin-left: 0;
      margin-bottom: 25px;
    }
  }
  &-wrapper {
    position: relative;
    inline-size: 100%;
    &:before {
      content: "";
      display: block;
      padding-block-start: 56.25%;
    }
  }
  &-iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}

.modal__content {
  overflow: scroll;
}

@media screen and (max-width:1000px){
}
</style>
