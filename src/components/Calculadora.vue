<script setup>
const props = defineProps(["valor1", "valor2", "calcular", "operador"]);
const emit = defineEmits(["calculate"]);
import { ref } from "vue";

const number_1 = ref(0);
const number_2 = ref(0);
const operator = ref(null)
</script>

<template>
  <h2 class="text-center">Calculadora Aritmética</h2>
  <hr />
  <br />

  <div class="row">
    <div class="col-4 text-center">
      <label class="">NUMERO 1</label>
      <input type="number" v-model="number_1" class="form-control" />
    </div>
    <div class="col-4 text-center">
      <label class="">NUMERO 2</label>
      <input type="number" v-model="number_2" class="form-control" />
    </div>

    <div class="col-4 text-center">
      <label>OPERADOR</label>
      <select class="form-control" v-model="operator"
        @change="emit('calculate', { n1: number_1, n2: number_2, operator: operator })">
        <option class="text-center" value="+">+ ADIÇÃO</option>
        <option class="text-center" value="-">- SUBTRAÇÃO</option>
        <option class="text-center" value=""> MULTIPLICAÇÃO</option>
        <option class="text-center" value="/">/ DIVISÃO</option>
      </select>
    </div>
  </div>
</template>