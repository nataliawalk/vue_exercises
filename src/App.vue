<script setup>
import { reactive, ref, computed } from 'vue'

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


let id = 0
const newTodo = ref('')
const hideCompleted = ref(false)
const todos = ref([
  { id: id++, text: 'Learn HTML', done: true },
  { id: id++, text: 'Learn JavaScript', done: true },
  { id: id++, text: 'Learn Vue', done: false }
])

const filteredTodos = computed(() => {
  return hideCompleted.value ? todos.value.filter((t) => !t.done) : todos.value
})

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, done: false })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
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


  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>


</template>

<style>
.title {
  color: blue;
}
.done {
  text-decoration: line-through;
}
</style>