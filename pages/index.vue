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
      </p>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
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
</style>
