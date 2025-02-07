<template>
    <div>
        <SliderComponent
        v-for="ingredient in ingredients"
        :key="ingredient.name"
        :ingredient="ingredient"
        @update="updateIngredient">
    </div>
</template>

<script setup>
    import { reactive, ref } from "vue";
    import { sliderComponent } from "./SliderComponent.vue";

    const ingredients = ref([
        { name: "Flour", min: 200, max: 500, moistureMultiplier: -0.5, sweetMultiplier: 0},
        { name: "Bananas", min: 1, max: 5, moistureMultiplier: 50, sweetMultiplier: 20},
        { name: "Egg", min: 1, max: 3, moistureMultiplier: 20, sweetMultiplier: 20},
    ]);
</script>

<style lang="scss" scoped>

</style>