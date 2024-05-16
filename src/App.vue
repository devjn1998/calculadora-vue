<script setup>
import { reactive } from 'vue';
import Calculadora from './components/Calculadora.vue';
import Resultado from './components/Resultado.vue';

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
    <Calculadora :calcular="calcular" :operador="estado.operador" :valor1="estado.valor1" :valor2="estado.valor2" ></Calculadora>
    <Resultado :resultado="estado.resultado"></Resultado>
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