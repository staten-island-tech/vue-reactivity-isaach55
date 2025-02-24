<template>
  <div id="resultsContainer">
    <div id="slider">
    <p>SAMANTHA ANALYSIS:</p>
    <div v-show="props.rating == 0">
      <p>banana bread? YUMMY YUMMY! Either you haven't made something yet or it is an impressive 0/5!!!!</p>
      <img src="/SamanthaJeff.png" alt="Samantha Jeff">
    </div>
    <div v-show="rating == 1">
      <img src="/Samantha1.png" alt="Samantha is disgusted." />
      <p>So sorry to hear about this terrible excuse for a banana bread, your banana bread gets 1 BIG BOOM! BOOM! Making something this bad should be a criminal offense it would actually kill someone </p>
    </div>
    <div v-show="rating == 2">
      <img src="/Samantha2.png" alt="Samantha is slightly disgusted." />
      <p>So sorry to hear about this terrible excuse for a banana bread, your banana bread gets 2 BIG BOOMS! BOOM! BOOM! Samantha says your banana bread is disgusting </p>
    </div>
    <div v-show="rating == 3">
      <img src="/Samantha3.png" alt="Samantha is conflicted." />
      <p>Your banana bread gets 3 BIG BOOMS! BOOM! BOOM! BOOM! It's alright, but Samantha won't enjoy this mediocre banana bread</p>
    </div>
    <div v-show="rating == 4">
      <img src="/Samantha4.png" alt="Samantha is happy." />
      <p>Your banana bread gets 4 BIG BOOMS! BOOM! BOOM! BOOM! BOOM! Samantha approved she would eat this</p>
    </div>
    <div v-show="rating == 5">
      <img src="/Samantha5.png" alt="The samantha is pleased" />
      <p>Your banana bread gets 5 BIG BOOMS! BOOM! BOOM! BOOM! BOOM! BOOM! Samantha loves this banana bread! </p>
    </div>
    </div>
  </div>
</template>

<script setup>
import {  defineProps } from 'vue';
const props = defineProps({ rating: Number })
</script>

<style scoped>
#resultsContainer {
  display: flex;
  color: black;
  background-color: #eee3ab;
  border-radius: 1vw;
  flex-direction: column;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

#resultsContainer img {
  width: 100%;
}

#slider {
  box-sizing: border-box;
  overflow-y: scroll;
  scrollbar-width: thin;
  padding: 1vw;
  width: 100%;
  height: 100%;
}

</style>
