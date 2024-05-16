<script setup>
import { reactive } from 'vue';

const estado = reactive({
  resultado: '',
  valor1: '',
  valor2: '',
  operador: '',
  operadores: [],
})

const somar = (n1, n2) => {
  return n1 + n2;
}
const subtrair = (n1, n2) => {
  return n1 - n2;
}
const multiplicar = (n1, n2) => {
  return n1 * n2;
}
const dividir = (n1, n2) => {
  return n1 / n2;
}

const calcular = () => {
  const { valor1, valor2, operador } = estado
  let resultado = ''

  if (operador === '+') {
    resultado = somar(parseFloat(valor1), parseFloat(valor2))
  } else if (operador === '-') {
    resultado = subtrair(parseFloat(valor1), parseFloat(valor2))
  } else if (operador === '*') {
    resultado = multiplicar(parseFloat(valor1), parseFloat(valor2))
  } else if (operador === '/') {
    resultado = dividir(parseFloat(valor1), parseFloat(valor2))
  }

  estado.resultado = resultado
}

</script>

<template>
  <div class="container">
    <h2 class="text-center">Calculadora Aritmética</h2>
    <hr>
    <br>
    <div class="row">
      <div class="col-4 text-center">
        <label class="">NUMERO 1</label>
        <input type="number" v-model="estado.valor1" @input="calcular" class="form-control">
      </div>
      <div class="col-4 text-center">
        <label class="">NUMERO 2</label>
        <input type="number" v-model="estado.valor2" @input="calcular" class="form-control">
      </div>
      <div class="col-4 text-center">
        <label>OPERADOR</label>
        <select class="form-control" v-model="estado.operador" @change="calcular">
          <option class="text-center" value="+">+ ADIÇÃO</option>
          <option class="text-center" value="-">- SUBTRAÇÃO</option>
          <option class="text-center" value="*">* MULTIPLICAÇÃO</option>
          <option class="text-center" value="/">/ DIVISÃO</option>
        </select>
      </div>
    </div>
    <br>
    <br>
    <hr>
    <div class="resultado-div text-center">
      <h2>RESULTADO:</h2>
      <br>
      <div class="resultado text-center col-4">
        <h2>O resultado é <span id="resultado">{{ estado.resultado }}</span></h2>
      </div>
    </div>

  </div>
</template>

<style scoped>
select {
  font-weight: bold;

  option {
    font-weight: bold
  }
}

.resultado-div {
  max-width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.resultado {
  max-width: 100%;
  background-color: rgb(49, 153, 49);
  padding: 28px;
  color: white;
  border-radius: 12px;
  
}
</style>
