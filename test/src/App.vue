<script setup>
import { ref } from 'vue'

let isDarkTheme = ref(false)

let imageSize = ref(300)

let inputText = ref('')
let text_mail = 'gmail.com'
</script>

<template>
  <div :class="{ 'is-dark': isDarkTheme }">
    <h1 class="display-3 text-center mt-5">Hello</h1>

    <p class="text-center my-3">
      <button @click="isDarkTheme = !isDarkTheme" class="btn btn-primary">
        Change website theme
      </button>
    </p>
    <div class="text-center my-2">
      <h2 class="display-4">Вводим текст в поле</h2>
    </div>

    <div class="row justify-content-center">
      <input class="form-control w-50" v-model="inputText" type="text" />
    </div>
    <p v-if="!inputText" class="fw-bold text-center">{{ inputText }}</p>
    <p v-else class="fw-bold text-center">{{ inputText + text_mail }}</p>
  </div>
</template>

<style scoped>
.is-dark {
  background: black;
  color: white;
}
</style>
