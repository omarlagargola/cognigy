<template>
  <div class="rating">
    <span v-for="(index, value) in [0,1,2,3,4]" :key="index" :class="{'active': index <= rating}" @click="rate(index)">*</span>
  </div>
</template>

<script setup>
  import { ref } from 'vue'
  
  const rating = ref(-1);
  
  const rate = (index) => {
    rating.value = index;
  };
</script>

<style>
  span{
    cursor: pointer;
  }
</style>
