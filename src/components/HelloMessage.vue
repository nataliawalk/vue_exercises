<script setup>
import { ref } from 'vue'

const textHeader = ref('hello')
const titleClass = ref('title')
</script>

<template>
  <h1 :class="titleClass">{{ textHeader }}</h1>
</template>

<style scoped>
.title {
  color: blue;
}
</style>