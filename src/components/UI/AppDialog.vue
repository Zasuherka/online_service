<template>
  <div class="dialog" v-if="show" @click="hideDialog">
    <div @click.stop class="dialog__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>

export default {
  name: 'app-dialog',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    hideDialog () {
      this.$emit('update:show', false)
    }
  }
}
</script>

<style>
.dialog {
  z-index: 200;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.dialog__content {
  margin: auto;
  padding: 40px;
  background: white;
  border-radius: 12px;
  min-width: 300px;
}
</style>
