<script setup>
import { ref } from 'vue'

const styles = ref([
  { backgroundColor: '#cadaba' },
  { backgroundColor: '#ebc2af' },
  { backgroundColor: '#dabdab' },
  { backgroundColor: '#d8bfd8' },
  { backgroundColor: '#c0c0c0' },
  { backgroundColor: '#ff6347' },
  { backgroundColor: '#00a86b' },
  { backgroundColor: '#5b92e5' },
  { backgroundColor: '#cd7f32' },
  { backgroundColor: '#00008b' },
  { backgroundColor: '#310062' },
  { backgroundColor: '#000000' },
])

const textColor = ref('#000000')

const changeTextColor = (color) => {
  textColor.value = color
}
</script>

<template>
  <div>
    <span :style="{ color: textColor }"
      >Lorem ipsum dolor, sit amet consectetur adipisicing elit. Tempore, magni!</span
    >
  </div>
  <select name="color" @change="changeTextColor($event.target.value)">
    <option
      v-for="style in styles"
      :key="style.backgroundColor"
      :style="{ backgroundColor: style.backgroundColor }"
      :value="style.backgroundColor"
    ></option>
  </select>
</template>

<style></style>
