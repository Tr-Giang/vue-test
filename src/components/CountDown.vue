<template>
  <button @click="start">start</button>
  <button @click="pause">pause</button>
  <button @click="reset">reset</button>
</template>

<script>
export default {
  emits: ['start', 'pause', 'reset'],
  methods: {
    start() {
      this.$emit('start');
    },
    pause() {
      this.$emit('pause');
    },
    reset() {
      this.$emit('reset');
    },
  },
};
</script>

<style></style>
