<script setup>
import { reactive } from 'vue'

const counter = reactive({ count: 5 })
</script>

<template>
    <p>Count is: {{ counter.count }}</p>
</template>