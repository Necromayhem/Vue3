<script setup>
import { computed } from "vue";

const props = defineProps({
  operation: {
    type: String,
    default: "+",
  },
  activeOperation: {
    type: String,
  },
});

const emit = defineEmits(["click"]);

const klass = computed(() => {
  return {
    "btn-primary": props.operation == props.activeOperation,
    "btn-outline-primary": props.operation != props.activeOperation,
  };
});
</script>

<template>
  <button @click="emit('click')" class="btn w-50" :class="klass">
    {{ operation }}
  </button>
</template>
