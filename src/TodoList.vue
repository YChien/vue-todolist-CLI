<template>
  <div>
    <input class="item" type="text" v-model="inputValue">
    <button @click="handleAdd">添加</button>
    <ul>
      <todo-item
        v-for="(value, index) in list"
        :key="index"
        :content="value"
        :index="index"
        @delete="handleDelete"
      ></todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem";

export default {
  components: {
    "todo-item": TodoItem
  },
  data() {
    return {
      inputValue: "",
      list: []
    };
  },
  methods: {
    handleAdd() {
      this.list.push(this.inputValue);
      this.inputValue = "";
    },
    handleDelete(index) {
      this.list.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
