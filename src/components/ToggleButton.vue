<script setup>
import { ref } from 'vue'
const awesome = ref(true)

function toggle() {
  awesome.value = !awesome.value
}
</script>

<template>
    <button @click="toggle">toggle</button>
    <h2 v-if="awesome">Vue is awesome!</h2>
    <h2 v-else>Oh no 😢</h2>
</template>