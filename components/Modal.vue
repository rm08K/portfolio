<template>
  <transition name="modal" appear>
    <div class="modal__overlay" @click.self="closeModal">
      <div class="modal__window">
        <div class="modal__content">
          <slot />
        </div>
      </div>
    </div>
  </transition>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  methods: {
    closeModal() {
      this.$emit('close-modal')
    }
  }
})
</script>

<style lang="scss" scoped>
.modal {
  &__overlay {
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    z-index: 100;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background: rgba(0, 0, 0, 0.3);
  }

  &__window {
    height: 80%;
    width: 80%;
    overflow: hidden;
    background-color: white;
  }

  &__content {
    height: calc(100% - 60px);
    padding: 20px;
  }
}

// transition
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.4s;
  .modal__window {
    transition: opacity 0.4s, transform 0.4s;
  }
}
.modal-leave-active {
  transition: opacity 0.6s ease 0.4s;
}
.modal-enter,
.modal-leave-to {
  opacity: 0;
  .modal__window {
    opacity: 0;
    transform: translateY(-20px);
  }
}
</style>
