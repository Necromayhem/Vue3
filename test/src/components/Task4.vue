<script setup>
import { ref } from 'vue'

const text_notice = ref('')
const show_text = ref('')
let timeoutId = null

const call_notice = () => {
  show_text.value = text_notice.value

  if (timeoutId) {
    clearTimeout(timeoutId)
  }

  timeoutId = setTimeout(() => {
    text_notice.value = ''
    show_text.value = ''
  }, 5000)
}
</script>

<template>
  <div>
    <input v-model="text_notice" type="text" placeholder="Введите уведомление" />
    <div><button @click="call_notice">Показать уведомление</button></div>
    <span>{{ show_text }}</span>
  </div>
</template>
