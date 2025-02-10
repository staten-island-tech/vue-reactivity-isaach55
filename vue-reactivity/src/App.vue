<template>
  <header>
    <div>
      <h1>
        Make some banana bread except I'm too lazy to provide a visual! You get friendly and
        constructive criticism here: :D
      </h1>
      <p>Most recent feedback:</p>
    </div>
    <IngredientsArray />
    <h1>5 BIG BOOMS! BOOM BOOM BOOM BOOM BOOM</h1>
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
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    width: 100%;
  }
}
</style>
