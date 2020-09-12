<template>
  <li class="item">
    <span @click.stop="done" :class="{done:isDone}">{{item}}</span>
    <div class="item-buttons">
      <button @click="del">Delete</button>
    </div>
  </li>
</template>

<script>
export default {
  data() {
    return { isDone: false };
  },
  name: "item",
  props: ["item", "index"],
  methods: {
    del() {
      this.$emit("del", this.index);
      this.isDone = false;
    },
    done() {
      this.isDone = !this.isDone;
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
}

span {
  cursor: pointer;
  flex: 1;
  overflow-wrap: anywhere;
  margin-right: 0.5rem;
}

.done {
  text-decoration-line: line-through;
  color: gray;
}

.item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}
</style>