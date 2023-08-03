<template>
  <div id="app">
    <img alt="Vue logo" src="https://vuejs.org/images/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->

    <div class="count-down">
      <count-down @start="onstart" @pause="onpause" @reset="onreset" />
      <p>{{ count }}</p>
    </div>

    <to-do />

    <test-doc />

    <color-box />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import CountDown from './components/CountDown.vue';
import ToDo from './components/ToDo.vue';
import TestDoc from './components/TestDoc.vue';
import ColorBox from './components/ColorBox.vue';

export default {
  name: 'App',
  data() {
    return {
      count: 60,
      varInterval: null,
    };
  },
  components: {
    HelloWorld,
    CountDown,
    ToDo,
    TestDoc,
    ColorBox,
  },
  methods: {
    onstart() {
      if (!this.varInterval) {
        this.varInterval = setInterval(() => {
          this.count -= 1;
        }, 1000);
      }
    },
    onpause() {
      if (!!this.varInterval) {
        clearInterval(this.varInterval);
        this.varInterval = null;
      }
    },
    onreset() {
      if (!!this.varInterval) {
        clearInterval(this.varInterval);
        this.varInterval = null;
      }
      this.count = 60;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

img {
  width: 50%;
}
</style>
