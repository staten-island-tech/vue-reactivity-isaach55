<template>
  <div id="mainContainer">
    <FeedbackBox :feedbackText="feedback"/>
    <IngredientsArray @updateMessage="updateFeedback"/>
    <h1 id="testText">hi some text is supposed to go here later</h1>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import IngredientsArray from './components/icons/IngredientsArray.vue';
import FeedbackBox from './components/icons/FeedbackBox.vue';

const feedback = ref("");
function updateFeedback(message) {
  console.log("feedback being updated: ", message);
  feedback.value = message;
}

</script>

<style scoped>
#mainContainer {
  display: flex;
  line-height: 1.5;
  height: 100vh;
  width: 100%;
  box-sizing: border-box;
  background-color: #3d2b03;
  display: flex;
  align-items: center;
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
