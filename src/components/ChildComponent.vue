<script setup>
import { ref } from 'vue';

const emit = defineEmits(['addNumber', 'resetNumber'])

const addAmount = ref()

function emitWithParameter(){
    emit('addNumber', addAmount.value)
    addAmount.value = null
}

</script>

<template>
  <div class="bg-blue-100 border-light-blue-200 rounded-2xl font-extrabold p-5">
    <div class="pb-3" >Componente hijo</div>
    <input
      v-model="addAmount"
      type="number"
      placeholder="Agrega la cantidad a sumar"
      class="w-full rounded-md py-2.5 px-4 border text-sm outline-[#007bff] mb-3"
    /> 
    <button
      type="button"
      class="text-white bg-[#007bff] hover:bg-blue-600 font-semibold rounded-md mb-3 text-sm px-4 py-2.5 w-full"
      @click="emitWithParameter()"
    >
      Sumar 1
    </button>
    <button
      type="button"
      class="text-grey bg-gray-200 hover:bg-blue-600 font-semibold rounded-md text-sm px-4 py-2.5 w-full"
      @click="emit('resetNumber')"
    >
      Resetear
    </button>
  </div>
</template>
