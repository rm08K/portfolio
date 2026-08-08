<template>
  <img class="self-port" src="/images/self.png" alt="自画像" />
</template>

<style scoped>
.self-port {
  block-size: 300px;
  animation: appear 1s;
}

@keyframes appear {
  from {
    opacity: 0;
  }
}
</style>
