<script setup>
import { ref } from 'vue'

const user_name = ref('')
const greetingsMessage = ref('')

const greetings = () => {
  greetingsMessage.value = 'Привет, ' + user_name.value + '!'
  user_name.value = ''
}
</script>

<template>
  <div>
    <form @submit.prevent="greetings">
      <label>Ваше имя:</label>
      <input v-model="user_name" type="text" />
      <input type="submit" value="Отправить" />
    </form>
  </div>
  <div>
    <span>{{ greetingsMessage }}</span>
  </div>
</template>

<style></style>
