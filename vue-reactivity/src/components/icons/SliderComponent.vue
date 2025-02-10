<template>
  <div>
    <label> {{ ingredient.name }}: {{ itemAmount }} grams</label>
    <input type="range" :min="ingredient.min" :max="ingredient.max" v-model="itemAmount" step="1" />
    <button @click="takeSliderValue">Use</button>
    <p>Used value: {{ usedValue }}g</p>
  </div>
</template>

<script setup>
import { defineProps, ref } from 'vue'

const props = defineProps({ ingredient: Object })
let itemAmount = ref(props.ingredient.min)
if (props.ingredient.amount) {
  itemAmount.value = ref(props.ingredient.amount)
}
const usedValue = ref(0)
function takeSliderValue() {
  usedValue.value = itemAmount.value
  //if usedValue.value > ref(props.ingredient.excessive)
}
</script>

<style lang="scss" scoped></style>
