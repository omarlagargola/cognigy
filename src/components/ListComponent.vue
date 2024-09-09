<template>
  <ul>
    <li v-for="(item, index) in dataItems" :key="index" @click="setToTop(index)">
      {{ item }}
    </li>
  </ul>
</template>

<script setup>
  import { ref } from 'vue'
  const props = defineProps(['items']);
  
  const dataItems = ref(props.items);

  const setToTop = (index) => {
    const toTop = dataItems.value.splice(index, 1);
    dataItems.value.unshift(...toTop);
  }
</script>

<style>
  li{
    cursor: pointer;
  }
</style>
