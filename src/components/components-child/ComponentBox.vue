<template>
  <div class="box-item" @click="showColor(myprop)"></div>
</template>

<script>
export default {
  methods: {
    showColor(color) {
      alert(color);
    },
  },
  props: ['myprop'],
};
</script>

<style>
.box-item {
  width: 150px;
  height: 150px;
  border: 1px solid #000;
  background-color: gray;
  border-radius: 10px;
}
</style>
