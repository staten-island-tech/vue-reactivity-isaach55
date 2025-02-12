<template>
  <div id="mainContainer">
    <div id="textContainer">
      <FeedbackBox :feedbackText="feedback" />
      <ResultsBox />
    </div>
    <IngredientsArray @updateMessage="updateFeedback" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import IngredientsArray from './components/icons/IngredientsArray.vue'
import FeedbackBox from './components/icons/FeedbackBox.vue'
import ResultsBox from './components/icons/ResultsBox.vue'

const feedback = ref('')
function updateFeedback(message) {
  console.log('feedback being updated: ', message)
  feedback.value = message
}
</script>

<style scoped>
#mainContainer {
  display: flex;
  line-height: 1.5;
  height: 100vh;
  box-sizing: border-box;
  background-color: #0f0a00;
  display: flex;
  align-items: center;
}

#textContainer {
  display: flex;
  flex-direction: column;
  height: 90vh;
  margin: 1vw;
  width: 50vw;
  align-items: center;
}
</style>
