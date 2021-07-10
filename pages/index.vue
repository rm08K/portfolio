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
              <div class="flexboxContainer-modal">
                <h3>デジタルハリウッド大学のWebデザイン・開発を知るサイト</h3>
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
              <div>
                <h3>Bデジタルハリウッド大学のWebデザイン・開発を知るサイト</h3>
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
              <div>Cモーダルの内容</div>
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

.modal__content {
  overflow: scroll;
}

@media screen and (max-width:1000px){
}
</style>
