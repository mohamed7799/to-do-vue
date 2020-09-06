<template>
  <li class="item">
    <span>{{item}}</span>
    <div class="item-buttons">
      <button @click="del">Delete</button>
    </div>
  </li>
</template>

<script>
export default {
  name: "item",
  props: ["item", "index"],
  methods: {
    del() {
      this.$emit("del", this.index);
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
.item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}
</style>