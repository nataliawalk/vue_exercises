<script setup>
import { ref } from 'vue'

const titleClass = ref('title')
</script>

<template>
  <h1 :class="titleClass">Make me green</h1>
</template>

<style>
.title {
  color: green;
}
</style>