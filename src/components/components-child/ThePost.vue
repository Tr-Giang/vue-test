<template>
  <ul>
    <li v-if="!items.length">Loading...</li>
    <li v-for="(item, idx) in items" :key="idx">
      <slot name="item" v-bind="item" />
      <button @click="handleLike(idx)">like</button>
      <button @click="item.likes--">dislike</button>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { body: 'Scoped Slots Guide', username: 'Evan You', likes: 20 },
        { body: 'Vue Tutorial', username: 'Natalia Tepluhina', likes: 10 },
      ],
    };
  },

  methods: {
    handleLike(idx) {
      this.items[idx].likes++;
    },
  },
};
</script>

<style>
ul {
  list-style-type: none;
  padding: 5px;
  background: linear-gradient(315deg, #42d392 25%, #647eff);
}
li {
  padding: 5px 20px;
  margin: 10px;
  background: #fff;
}
</style>
