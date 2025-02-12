<template>
  <div id="feedbackContainer">
    <h1>
      Make some banana bread except I'm too lazy to provide a visual! You get friendly and
      constructive feedback here: :D
    </h1>
    <br />
    <h2>Your most recent feedback: {{ feedbackText }}</h2>
  </div>
</template>

<script setup>
import { ref, defineProps } from 'vue'

const props = defineProps({ feedbackText: String })
</script>

<style scoped>
#feedbackContainer {
  color: black;
  height: 20vh;
  background-color: #eee3ab;
  box-sizing: border-box;
  padding: 1vw;
  border-radius: 1vw;
  flex-direction: column;
  width: 100%;
}
</style>
