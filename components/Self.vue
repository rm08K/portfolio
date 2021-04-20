<template>
  <img class="selfPort" src="~/assets/self.png" alt="自画像">
</template>

<style>
.selfPort {
  animation: 1s appear;
  /* margin: auto; */
  block-size: 300px;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>
