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
        パソコンが好きで色々やっています。
        <br>Webを勉強しています。好きなものを作りたい。
        <br>動画の編集もやったりしてます。
      </p>
    </div>
    <div class="secondView white">
      <h2 class="subTitle">
        works
      </h2>
      <div class="flexboxContainer">
        <div class="flexboxContainer-contents">
          <img class="flexboxContainer-contents_img" src="images/website/website_small_1.jpg" alt="">
        </div>
        <div class="flexboxContainer-contents">
          <img class="flexboxContainer-contents_img" src="images/website/website_small_2.jpg" alt="">
        </div>
        <div class="flexboxContainer-contents">
          <img class="flexboxContainer-contents_img" src="images/website/youtube1.jpg" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
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
    }
  }
}
@media screen and (max-width:1000px){
}
</style>
