<template>
  <header>
    <div id="testDiv">
      <h1>
        Make some banana bread except I'm too lazy to provide a visual You get friendly and
        constructive criticism here: :D
      </h1>
      <p>Most recent feedback:</p>
    </div>
    <IngredientsArray />
    <h1 id="testText">hi some text is supposed to go here later</h1>
  </header>
</template>

<script setup>
import IngredientsArray from './components/icons/IngredientsArray.vue'
</script>

<style scoped>
header {
  display: flex;
  line-height: 1.5;
  max-height: 100vh;
  width: 100%;
  box-sizing: border-box;
  background-color: #3d2b03;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    align-items: center;
    width: 100%;
  }
}

#testDiv {
  box-sizing: border-box;
  border-radius: 1vw;
  height: 90vh;
  background-color: #e3c567;
  color: white;
}

#testText {
  color: white;
}
</style>
