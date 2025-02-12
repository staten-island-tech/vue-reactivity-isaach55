<template>
  <div class="slider">
    <label> {{ ingredient.name }}: {{ itemAmount }} grams</label>
    <input type="range" :min="ingredient.min" :max="ingredient.max" v-model="itemAmount" step="1" />
    <button @click="takeSliderValue">Use</button>
    <p>Used value: {{ usedValue }}g</p>
  </div>
</template>

<script setup>
import { defineProps, ref, defineEmits } from 'vue'

const props = defineProps({ ingredient: Object });
const emit = defineEmits(["updateMessage"]);
const itemAmount = ref(props.ingredient.min);
if (props.ingredient.amount) {
  itemAmount.value = props.ingredient.amount;
}
const usedValue = ref(props.ingredient.min);
function takeSliderValue() {
  usedValue.value = itemAmount.value;
  if (usedValue.value > props.ingredient.excessive) {
    console.log("Emitting feedback:", props.ingredient.message);
    emit("updateMessage", props.ingredient.message);
  }
}
</script>

<style scoped>
.slider {
  background-color: #eee3ab;
  box-sizing: border-box;
  padding: 1vw;
  margin: 1vw 0;
  border-radius: 1vw;
  flex-direction: column;
}
</style>
