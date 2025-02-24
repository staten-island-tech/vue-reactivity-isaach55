<template>
  <div id="feedbackContainer">
    <div id="slider">
      <h2>
        Make some banana bread except I'm too lazy to provide a visual! This is a friendly constructive criticism box :D
      </h2>
      <br />
      <h3>Latest feedback: {{ feedbackText }}</h3>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({ feedbackText: String })
</script>

<style scoped>
#feedbackContainer {
  color: black;
  height: 20vh;
  background-color: #eee3ab;
  box-sizing: border-box;
  border-radius: 1vw;
  display: flex;
  flex-direction: column;
  width: 100%;
  overflow: hidden;
}
#slider {
  overflow-y: scroll;
  scrollbar-width: thin;
  padding: 0.5vw;
}
</style>
