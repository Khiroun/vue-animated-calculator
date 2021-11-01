<template>
  <div id="app">
    <Bubbles />
    <CalculatorContainer />
  </div>
</template>

<script>
import Bubbles from "./components/BubblesCollection.vue";
import CalculatorContainer from "./components/CalculatorContainer.vue";
export default {
  name: "App",
  components: {
    Bubbles,
    CalculatorContainer,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}
body {
  height: 100vh;
  width: 100%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(#2196f3, #e91e63);
}
</style>
