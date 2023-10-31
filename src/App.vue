<script setup>
import { reactive, ref } from 'vue'

const textHeader = ref('hello')
const titleClass = ref('title')

const counter = reactive({ count: 5 })
const count = ref(0)

const text = ref('')

const awesome = ref(true)

function toggle() {
  awesome.value = !awesome.value
}

function onInput(e) {
  text.value = e.target.value
}

function increment() {
  count.value++
}

</script>

<template>
  <h1 :class="titleClass">{{ textHeader }}</h1>
  <p>Count is: {{ counter.count }}</p>
  <button @click="increment">count is: {{ count }}</button>
  <br><br>
  <input :value="text" @input="onInput" placeholder="Type here">
  <p>{{ text }}</p>
  <button @click="toggle">toggle</button>
  <h2 v-if="awesome">Vue is awesome!</h2>
  <h2 v-else>Oh no 😢</h2>
</template>

<style>
.title {
  color: blue;
}
</style>