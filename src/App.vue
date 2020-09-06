<template>
  <div id="app">
    <Title />
    <List />
    <Footer />
  </div>
</template>

<script>
import Title from "./components/title";
import List from "./components/list";
import Footer from "./components/footer";

export default {
  name: "App",
  components: { Title, List, Footer },
};
</script>

<style>
html,
body {
  height: 100%;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#app {
  height: 100%;
  display: flex;
  flex-direction: column;
}

button {
  padding: 0.5rem 1rem;
  background-color: purple;
  color: white;
  cursor: pointer;
  border: none;
  border-radius: 5px;
  outline-color: purple;
}
</style>
