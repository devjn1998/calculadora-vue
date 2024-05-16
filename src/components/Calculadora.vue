<script setup>
const props = defineProps(['valor1', 'valor2', 'calcular', 'operador'])
</script>

<template>

    <h2 class="text-center">Calculadora Aritmética</h2>
    <hr>
    <br>
    <div class="row">
      <div class="col-4 text-center">
        <label class="">NUMERO 1</label>
        <input type="number" v-model="props.valor1" @input="props.calcular" class="form-control">
      </div>
      <div class="col-4 text-center">
        <label class="">NUMERO 2</label>
        <input type="number" v-model="props.valor2" @input="props.calcular" class="form-control">
      </div>
      <div class="col-4 text-center">
        <label>OPERADOR</label>
        <select class="form-control" v-model="props.operador" @change="props.calcular">
          <option class="text-center" value="+">+ ADIÇÃO</option>
          <option class="text-center" value="-">- SUBTRAÇÃO</option>
          <option class="text-center" value="*">* MULTIPLICAÇÃO</option>
          <option class="text-center" value="/">/ DIVISÃO</option>
        </select>
      </div>
    </div>
</template>
