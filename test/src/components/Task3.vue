<script setup>
import { ref } from 'vue'

const input = ref('')

let id = Date.now()
const toDoList = ref([
  { id: 34244324, value: 'Изучить доку Vue' },
  { id: 234324324, value: 'Изучить доку TS' },
  { id: 234324324324, value: 'Изучить доку Nuxt' },
])

const addToDo = (event) => {
  event.preventDefault()
  toDoList.value.push({ id: globalThis.crypto.randomUUID(), value: input.value })
  input.value = ''
}

const deleteTodo = (toDo) => {
  toDoList.value = toDoList.value.filter((x) => x.id !== toDo.id)
}
</script>

<template>
  <div>
    <form>
      <input v-model="input" type="text" />
      <input @click="addToDo" type="submit" value="Добавить" />
    </form>
  </div>
  <div v-for="toDo in toDoList" :key="toDo">
    <span>{{ toDo.id }} </span>
    <span>{{ toDo.value }} </span>
    <button @click="deleteTodo(toDo)">x</button>
  </div>
</template>
