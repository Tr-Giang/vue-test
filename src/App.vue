<template>
  <div id="app">
    <img alt="Vue logo" src="https://vuejs.org/images/logo.png" />

    <test-slots>
      <template #header>This is header</template>
      <template #default>This is main content</template>
      <template #footer>This is footer</template>
    </test-slots>
    <my-component v-slot="infor">
      My name is {{ infor.myName }}, I am a {{ infor.job }}
    </my-component>

    <new-feed />
  </div>
</template>

<script>
import TestSlots from './components/TestSlots.vue';
import MyComponent from './components/MyComponent.vue';
import NewFeed from './components/NewFeed.vue';
export default {
  name: 'App',
  data() {
    return {
      count: 60,
      varInterval: null,
    };
  },
  components: {
    MyComponent,
    TestSlots,
    NewFeed,
  },
  methods: {},
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
