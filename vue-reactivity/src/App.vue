<template>
  <div id="mainContainer">
    <div id="textContainer">
      <FeedbackBox :feedbackText="feedback" />
      <br>
      <ResultsBox :rating="rating"/>
    </div>
    <IngredientsArray @updateMessage="updateFeedback" @updateRating="updateRating"/>
    <img src="" alt="">
  </div>
</template>

<script setup>
import { ref } from 'vue'
import IngredientsArray from './components/icons/IngredientsArray.vue'
import FeedbackBox from './components/icons/FeedbackBox.vue'
import ResultsBox from './components/icons/ResultsBox.vue'

const feedback = ref('')
const rating = ref(0)
function updateFeedback(message) {
  feedback.value = message
}
function updateRating(newRating) {
  console.log('Received new rating:', newRating)
  rating.value = newRating
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
  width: 50vw;
  align-items: center;
  margin: 0 2vw;
}
</style>
