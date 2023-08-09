<template>
  <the-post #item="{ body, username, likes }">
    <div class="item">
      <p>{{ body }}</p>
      <p class="meta">by {{ username }} | {{ likes }} likes</p>
      
    </div>
  </the-post>
</template>

<script>
import ThePost from './components-child/ThePost.vue';

export default {
  components: {
    ThePost,
  },
  methods: {
    
  },
};
</script>

<style></style>
