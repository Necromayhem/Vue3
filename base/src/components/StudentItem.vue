<script setup>
import { computed } from "vue";

const props = defineProps({
  student: {
    type: Object,
  },
});

const href = computed(() => {
  return "http://vk.com/id" + props.student.id;
});
</script>

<template>
  <div class="wrapper">
    <a :href="href" target="_blank">
      <img :src="student.photo_max_orig" alt="картинка" />
      {{ student.first_name }} {{ student.last_name }}
    </a>
  </div>
</template>

<style scoped>
img {
  width: 100px;
  height: 100px;
  object-fit: cover;
}

.wrapper {
  padding: 0.5rem;
  margin: 0.5rem 0;
  border: 1px solid silver;
}
</style>
