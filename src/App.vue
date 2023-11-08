<script setup>
import { ref } from 'vue'
import HelloMessage from './components/HelloMessage.vue'
import CounterText from './components/CounterText.vue'
import GreenText from './components/GreenText.vue'
import Counter from './components/Counter.vue'
import Form from './components/Form.vue'
import FormModel from './components/FormModel.vue'
import ToggleButton from './components/ToggleButton.vue'
import Todo from './components/Todo.vue'
import MountedText from './components/MountedText.vue'
import Watchers from './components/Watchers.vue'
import ChildCompComponents from './components/ChildCompComponents.vue'
import ChildCompProps from './components/ChildCompProps.vue'
import ChildCompEmits from './components/ChildCompEmits.vue'
import ChildCompSlots from './components/ChildCompSlots.vue'

const propsGreeting = ref('hello from parent')
const emitChildMsg = ref('no child msg yet')
const slotMessage = ref('from parent')
</script>

<template>
  <HelloMessage />
  <CounterText />
  <GreenText />
  <Counter />
  <br><br>
  <Form />
  <FormModel />
  <ToggleButton />
  <Todo />
  <MountedText />
  <Watchers />
  <ChildCompComponents />
  <ChildCompProps :msg="propsGreeting" />
  <ChildCompEmits @response="(emitMessage) => emitChildMsg = emitMessage" />
  <p>{{ emitChildMsg }}</p>
  <ChildCompSlots>Message: {{ slotMessage }}</ChildCompSlots>
</template>