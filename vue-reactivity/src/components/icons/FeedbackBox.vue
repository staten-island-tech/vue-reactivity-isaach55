<template>
  <div>
    <h1>
      Make some banana bread except I'm too lazy to provide a visual! You get friendly and
      constructive feedback here: :D
    </h1>
    <p>Your most recent feedback: {{ feedback }}</p>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import IngredientsArray from './IngredientsArray.vue'
</script>

<style lang="scss" scoped></style>
