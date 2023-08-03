<template>
  <div class="boxs">
    <component-box
      v-for="color in colors"
      :style="{ backgroundColor: color }"
      :key="color"
      :myprop="color"
    />
  </div>
</template>

<script>
import ComponentBox from './components-child/ComponentBox.vue';
export default {
  data() {
    return {
      colors: ['red', 'yellow', 'blue', 'green'],
    };
  },
  components: {
    ComponentBox,
  },
  methods: {},
};
</script>

<style>
.boxs {
  display: flex;
  flex-wrap: wrap;
}
</style>
