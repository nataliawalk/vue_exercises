<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['response'])

emit('response', 'message from child')
</script>

<template>
    <h2>child component</h2>
</template>
