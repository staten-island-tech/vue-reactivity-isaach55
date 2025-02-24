<template>
  <div id="sliderContainerOuter">
    <div id="sliderContainerInner">
      <SliderComponent
        v-for="ingredient in ingredients"
        :key="ingredient.name"
        :ingredient="ingredient"
        v-model="ingredient.amount"
        @updateMessage="forwardFeedback"
      />
      <button id="bakeButton" @click="showResults">Get Samantha rating</button>
    </div>
  </div>
</template>

<script setup>
import { ref , defineEmits } from 'vue'
import SliderComponent from './SliderComponent.vue'
import ResultsBox from './ResultsBox.vue'

const emit = defineEmits(['updateMessage', 'updateRating'])
function forwardFeedback(message) {
  emit('updateMessage', message)
}

const rating = ref(0)
function showResults() {
  let currentRating = 0
  if (180 < calculateTotal(ingredients, 'sweetMultiplier') && calculateTotal(ingredients, 'sweetMultiplier') < 250) {
    currentRating++
  }
  if (-20 < calculateTotal(ingredients, 'moistureMultiplier') && calculateTotal(ingredients, 'moistureMultiplier') < 50) {
    currentRating++
  }
  if (75 < calculateTotal(ingredients, 'oil') && calculateTotal(ingredients, 'oil') < 130) {
    currentRating++
  }
  if (6 < ingredients.value.find(ingredient => ingredient.name == 'Vanilla').amount && ingredients.value.find(ingredient => ingredient.name == 'Vanilla').amount < 13) {
    currentRating++
  }
  if (75 < ingredients.value.find(ingredient => ingredient.name == 'Egg').amount && ingredients.value.find(ingredient => ingredient.name == 'Egg').amount < 125) {
    currentRating++
  }
  rating.value = currentRating
  console.log('Emitting rating:', rating.value)
  emit('updateRating', rating.value)
}

function calculateTotal (ingredients, factor) {
  let total = 0
  ingredients.value.forEach(ingredient => {
    total += ingredient.amount * ingredient[factor]
  });
  return total
}

const ingredients = ref([
  {
    name: 'Flour',
    min: 100,
    max: 550,
    moistureMultiplier: -1,
    sweetMultiplier: 0,
    oil: 0,
    excessive: 325,
    amount: 100,
    message: 'this is going to be so dry are you making banana bread or mixing concrete',
  },
  {
    name: 'Banana',
    min: 200,
    max: 600,
    moistureMultiplier: 0.5,
    sweetMultiplier: 0.25,
    oil: 0,
    excessive: 500,
    amount: 200,
    message:
      'is there even going to be any bread in this banana bread?',
  },
  {
    name: 'Egg',
    min: 50,
    max: 200,
    moistureMultiplier: 1,
    sweetMultiplier: 0,
    oil: 0,
    excessive: 125,
    amount: 50,
    message: 'that much egg? in this economy?',
  },
  {
    name: 'Butter',
    min: 40,
    max: 180,
    moistureMultiplier: 0,
    sweetMultiplier: 0,
    oil: 1,
    excessive: 130,
    amount: 40,
    message: 'your banana bread is going to be so oily the US military would drill in it',
  },
  {
    name: 'Sugar',
    min: 60,
    max: 200,
    moistureMultiplier: -0.5,
    sweetMultiplier: 1,
    oil: 0,
    excessive: 140,
    amount: 60,
    message: 'this amount of sugar would make my asian parents go comatose',
  },
  {
    name: 'Vanilla',
    min: 1,
    max: 15,
    moistureMultiplier: 2,
    sweetMultiplier: 0,
    oil: 0,
    excessive: 12,
    amount: 1,
    message: 'this is not a normal amount of vanilla.',
  },
])

</script>

<style scoped>
#sliderContainerOuter {
  box-sizing: border-box;
  background-color: #d9ae61;
  border-radius: 1vw;
  margin: 2vw;
  overflow: hidden;
}

#sliderContainerInner {
  height: 90vh;
  overflow-y: scroll;
  scrollbar-width: thin;
  padding: 0 1vw;
}

#bakeButton {
  width: 100%;
  margin: 0 0 2vh 0;
  background-color: #ffd191;
  border-radius: 0.5vw;
  border-color: #ffd191;
}
</style>
