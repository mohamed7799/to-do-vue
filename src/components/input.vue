<template>
  <div id="input-box">
    <input v-model="newItem" type="text" placeholder="Enter your task here" />

    <button @click="add">Enter</button>
  </div>
</template>


<script>
export default {
  data() {
    return { newItem: "" };
  },
  methods: {
    add() {
      if (this.newItem === "") {
        alert("please enter a task");
      } else {
        this.$emit("add", this.newItem);
        this.newItem = "";
      }
    },
  },
};
</script>

<style scoped>
#input-box {
  width: 30%;
  margin-bottom: 1rem;
  display: flex;
}

input {
  padding: 0.5rem 1rem;
  border: 1px solid purple;
  border-radius: 5px;
  outline-color: purple;
  flex: 1;
  margin-right: 1rem;
}
</style>