<script setup>
import { onBeforeMount, ref, computed } from "vue";
import StudentItem from "@/components/StudentItem.vue";

const students = ref([]);
const filterText = ref("");

onBeforeMount(async () => {
  let r = await fetch("/students2022.json");
  let data = await r.json();
  students.value = data;
});

const filteredStudents = computed(() => {
  return students.value.filter((x) => {
    return (
      x.first_name.includes(filterText.value) ||
      x.last_name.includes(filterText.value)
    );
  });
});
</script>

<template>
  <div class="row m-2">
    <div class="col-12">
      <input
        placeholder="Фильтр"
        class="form-control"
        type="text"
        v-model="filterText"
      />
    </div>
  </div>

  <template v-for="s in filteredStudents" :key="s.id">
    <StudentItem :student="s" />
  </template>
</template>

<style></style>
