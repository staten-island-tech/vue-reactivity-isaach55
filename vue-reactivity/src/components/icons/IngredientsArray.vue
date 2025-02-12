<template>
  <div id="sliderContainerOuter">
    <div id="sliderContainerInner">
      <SliderComponent
        v-for="ingredient in ingredients"
        :key="ingredient.name"
        :ingredient="ingredient"
        @updateMessage="forwardFeedback"
      />
    </div>
  </div>
</template>

<script setup>
import { reactive, defineEmits } from 'vue'
import SliderComponent from './SliderComponent.vue'

const emit = defineEmits()
function forwardFeedback(message) {
  emit('updateMessage', message)
}
const ingredients = reactive([
  {
    name: 'Flour',
    min: 100,
    max: 550,
    moistureMultiplier: -1,
    sweetMultiplier: 0,
    oil: 0,
    excessive: 325,
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
    message:
      'is there even going to be any bread in this banana bread? this is banana with a side of bread',
  },
  {
    name: 'Egg',
    min: 50,
    max: 200,
    moistureMultiplier: 1,
    sweetMultiplier: 0,
    oil: 0,
    excessive: 125,
    message: 'that many eggs? in this economy?',
  },
  {
    name: 'Butter',
    min: 40,
    max: 180,
    moistureMultiplier: 0,
    sweetMultiplier: 0,
    oil: 3,
    excessive: 130,
    message: 'your banana bread is going to be so oily the US military would drill in it',
  },
  {
    name: 'Sugar',
    min: 60,
    max: 240,
    moistureMultiplier: -0.5,
    sweetMultiplier: 1,
    oil: 0,
    excessive: 140,
    message: 'the sugar... why?',
  },
  {
    name: 'Vanilla Extract',
    min: 1,
    max: 15,
    moistureMultiplier: 2,
    sweetMultiplier: 0,
    oil: 0,
    excessive: 12,
    message: 'this is not a normal amount of vanilla.',
  },
])

/*banana
all p flour, bread flour? -> this is so dry are you making banana bread or mixing concrete
egg -> that much egg? in this economy?
vanilla -> thats a lot of vanilla relax
sugar ->
honey ->      }}} if sweetness > something -> erm thats kind of a lot of sugar ERM thats kind of a LOT of sugar ERM THATS A LOT OF SuGAR
maple syrup ->
butter / oil -> your banana bread is so oily the united states military would drill in it
chocolate chips -> uhhh you got some banana in your chocolate bread thats more chocolate chips than samantha has hairs on her head
cinnamon ->
milk ->
salt -> this is almost as salty as you would be if you had Samantha as a teammate
baking powder -> put any more and this banana bread will be bigger than even samanthas forehead

winnie holding a gun to your head name 5 things that you could have done better just hand over the banana bread already
the only person that could make banana bread worse than this is samantha
id rather take ap literature and composition than eat this banana bread

THIS BANANA BREAD GETS 1-5 BIG BOOMS! BOOM BOOM BOOM BOOM BOOM

Verdict:

IDEAS:
sliders, interactive feedback?
*/
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
  scrollbar-color: #d9cfc1;
  padding: 0 1vw;
}
</style>
