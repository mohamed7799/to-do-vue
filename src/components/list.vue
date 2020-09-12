<template>
  <div class="list-container">
    <Input v-on:add="addItem($event)" />
    <ul>
      <Item
        :item="item"
        :index="ind"
        v-on:del="deleteItem($event)"
        :key="ind"
        v-for="(item,ind) in items"
      />
    </ul>
  </div>
</template>

<script>
import Input from "./input";
import Item from "./item";

export default {
  components: { Input, Item },
  name: "list",
  data() {
    return { items: ["task 1", "task 2", "task 3", "task 4", "task 5"] };
  },
  methods: {
    addItem(item) {
      this.items.push(item);
    },
    deleteItem(item) {
      this.items.splice(item, 1);
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
ul {
  display: block;
  border: 1px solid purple;
  border-radius: 5px;
  padding: 1rem;
  width: 30%;
  background-color: #e8e8e8;
}

.list-container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.item-buttons button {
  padding: 0.5rem 1rem;
  background-color: purple;
  color: white;
  cursor: pointer;
  border: none;
  border-radius: 5px;
  outline-color: purple;
}
</style>