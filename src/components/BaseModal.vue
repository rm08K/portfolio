<script setup lang="ts">
defineEmits<{
  close: []
}>()
</script>

<template>
  <Teleport to="body">
    <div class="modal-overlay" role="presentation" @click.self="$emit('close')">
      <section class="modal-window" role="dialog" aria-modal="true">
        <div class="modal-content">
          <slot />
        </div>
      </section>
    </div>
  </Teleport>
</template>

<style scoped>
.modal-overlay {
  position: fixed;
  inset: 0;
  z-index: 100;
  display: grid;
  place-items: center;
  background: rgb(0 0 0 / 30%);
}

.modal-window {
  inline-size: min(80%, 960px);
  block-size: 80%;
  overflow: hidden;
  background: #fff;
}

.modal-content {
  block-size: calc(100% - 40px);
  padding: 20px;
  overflow: auto;
}
</style>
