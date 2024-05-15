<script setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const count = ref(0);

function addNumber(toAdd) {
  count.value += toAdd ;
}
</script>

<template>
  <div class="p-24">
    <div
      class="p-8 bg-white rounded-3xl border-solid border-4 border-light-blue-500 text-[#333] font-[sans-serif]"
    >
      <h1 class="text-3xl font-extrabold">Componente Padre</h1>
      <div class="text-1xl pb-5">Conteo {{ count }}</div>
      <ChildComponent @addNumber="addNumber" @resetNumber="count = 0" />
    </div>
  </div>
</template>
