<template>
  <div
    class="static"
    v-bind:class="{ active: isActive, 'text-danger': hasError }"
  >
    hello
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: true,
      hasError: true,
    };
  },
};
</script>

<style></style>
