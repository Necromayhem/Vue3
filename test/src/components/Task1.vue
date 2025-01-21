<script setup>
import { ref } from 'vue'

const x = ref(0)

const incr = () => {
  x.value++
}
const decr = () => {
  x.value--
}
</script>

<template>
  <div>
    <span>{{ x }}</span>
  </div>
  <div>
    <button @click="incr">+</button>
    <button @click="decr">-</button>
  </div>
</template>

<style></style>
