<template>
  <input
    type="text"
    v-model="inputValue"
    ref="inputNode"
    @keydown.enter="onSubmit"
  />
  <button @click="onSubmit">Submit</button>
  <button @click="deleteAll">Clear All</button>

  <ul class="list">
    <li
      v-for="(item, index) in dataList"
      :key="index"
      :data-id="index"
      @click="completed"
    >
      {{ item.content }}
      <button @click.stop @click="onDelete">Delete</button>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      dataList: [
        {
          content: 'javascript',
          completed: false,
        },
      ],
      inputValue: '',
    };
  },
  methods: {
    onSubmit() {
      this.dataList.push({
        content: this.inputValue,
        completed: false,
      });
      this.inputValue = '';
      this.$refs.inputNode.value = '';
    },
    deleteAll() {
      this.dataList = [];
    },
    onDelete(e) {
      this.dataList.splice(e.target.parentNode.dataset.id, 1);
    },
    completed(e) {
      if (!e.target.classList.contains('done')) {
        e.target.classList.add('done');
        this.dataList[e.target.dataset.id].completed = true;
      } else {
        e.target.classList.remove('done');
        this.dataList[e.target.dataset.id].completed = false;
      }
    },
  },
};
</script>

<style>
li {
  display: block;
}
li:hover {
  cursor: pointer;
}
.done {
  text-decoration: line-through;
}
</style>
