<template>
    <div>
        <label> {{ ingredient.name }}: {{ ingredient.amount }} grams</label>
    <input type="range"
    :min = "ingredient.min"
    :max = "ingredient.max"
    v-model = "ingredient.amount"
    step = "1"
    >
    </div>
</template>

<script setup>
    import { defineProps } from "vue";

    const props = defineProps({ingredient: Object});
</script>

<style lang="scss" scoped>

</style>