<script setup>
import { ref, computed } from "vue";
import OperationButton from "@/components/OperationButton.vue";
import { OPERATIONS } from "@/constans";

let a = ref();
let b = ref();
let op = ref("");

let c = computed(() => {
  if (op.value == "+") return a.value + b.value;
  if (op.value == "-") return a.value - b.value;
  if (op.value == "*") return a.value * b.value;
  if (op.value == "/") return a.value / b.value;
});

function changeOperation(value) {
  op.value = value;
}
</script>

<template>
  <div class="container">
    <div class="row gy-2 mt-2">
      <div class="col-12">
        <input v-model="a" class="form-control" type="number" />
      </div>
      <div class="col-12">
        <input v-model="b" class="form-control" type="number" />
      </div>
      <div class="col-3" v-for="operation in OPERATIONS" :key="operation">
        <OperationButton
          @click="changeOperation(operation)"
          :operation="operation"
          :active-operation="op"
        />
      </div>

      <div class="col-12">
        <select v-model="op" class="form-select">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>
    </div>
    <hr />
    <span>
      {{ a }}
    </span>
    {{ op }}
    <span>
      {{ b }}
    </span>
    =
    <span>
      {{ c }}
    </span>
  </div>
</template>

<style></style>
