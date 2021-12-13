<template>
  <div id="app">
    <Counter/>
  </div>
</template>

<script>
import Counter from "./components/Counter";

export default {
  name: "App",
  components: {
    Counter
  }
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 160px;
}
</style>
