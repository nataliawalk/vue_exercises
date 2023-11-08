<script setup>
import { defineProps} from 'vue'

const props = defineProps({
    msg: String
})
</script>

<template>
    <h2>{{ props.msg || 'no props passed yet' }}</h2>
</template>
