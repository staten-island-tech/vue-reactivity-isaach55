<template>
  <div>
    <SliderComponent></SliderComponent>
    v-for="ingredient in ingredients" :key="ingredient.name" :ingredient="ingredient"
    @update="updateIngredient">
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'
import { sliderComponent } from './SliderComponent.vue'

const ingredients = ref([
  {
    name: 'Flour',
    min: 150,
    max: 550,
    moistureMultiplier: -1,
    sweetMultiplier: 0,
    oil: 0,
    message: 'this is going to be so dry are you making banana bread or mixing concrete',
  },
  {
    name: 'Bananas',
    min: 200,
    max: 600,
    moistureMultiplier: 0.5,
    sweetMultiplier: 0.25,
    oil: 0,
    message: "atp there isn't going to be any bread in your banana bread",
  },
  {
    name: 'Egg',
    min: 50,
    max: 150,
    moistureMultiplier: 1,
    sweetMultiplier: 0,
    oil: 0,
    message: 'that many eggs? in this economy?',
  },
  {
    name: 'Butter',
    min: 40,
    max: 140,
    moistureMultiplier: 0,
    sweetMultiplier: 0,
    oil: 0,
    message: 'your banana bread is so oily the US military would drill in it',
  },
  {
    name: 'Sugar',
    min: 50,
    max: 250,
    moistureMultiplier: -0.5,
    sweetMultiplier: 0,
    oil: 0,
    message: 'thats a lot of sugar!!!!!',
  },
  {
    name: 'Milk',
    min: 200,
    max: 500,
    moistureMultiplier: 2,
    sweetMultiplier: 0,
    oil: 0,
    message: 'you got some banana in your milk bread',
  },
  {
    name: 'Vanilla Extract',
    min: 1,
    max: 15,
    moistureMultiplier: 2,
    sweetMultiplier: 0,
    oil: 0,
    message: 'you got some banana in your milk bread',
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

IDEAS:
sliders, interactive feedback?
*/
</script>

<style lang="scss" scoped></style>
