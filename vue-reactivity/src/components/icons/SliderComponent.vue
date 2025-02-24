<template>
  <div class="sliderCard">
    <label class="label"> {{ ingredient.name }}: {{ itemAmount }} grams</label>
    <input
      class="slider"
      type="range"
      :min="ingredient.min"
      :max="ingredient.max"
      v-model="itemAmount"
      step="1"
    />
    <button @click="takeSliderValue">Use</button>
    <p>Used value: {{ usedValue }}g</p>
  </div>
</template>

<script setup>
import { defineProps, ref, defineEmits } from 'vue'

const props = defineProps({ ingredient: Object })
const emit = defineEmits(['updateMessage'])
const itemAmount = defineModel()
if (props.ingredient.amount) {
  itemAmount.value = props.ingredient.amount
}
const usedValue = ref(props.ingredient.min)
function takeSliderValue() {
  usedValue.value = itemAmount.value
  if (usedValue.value > props.ingredient.excessive) {
    emit('updateMessage', props.ingredient.message)
  }
}
</script>

<style scoped>
.sliderCard {
  background-color: #eee3ab;
  box-sizing: border-box;
  padding: 1vw;
  margin: 1vw 0;
  border-radius: 1vw;
  flex-direction: column;
}

.slider {
  align-self: center;
  width: 100%;
}

.label {
  width: 100%;
}
</style>
