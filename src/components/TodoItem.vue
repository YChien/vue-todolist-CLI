<template>
  <li class="item" @click="handleClick">{{content}}</li>
</template>

<script>
export default {
  props: ["content", "index"],
  methods: {
    handleClick() {
      this.$emit("delete", this.index);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>  /* 作用域 */
.item {
  color: rgb(13, 168, 34);
}
</style>
