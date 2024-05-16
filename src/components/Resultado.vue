<!-- Resultado.vue -->
<script setup>
const props = defineProps(['resultado'])

</script>

<template>
  <div class="resultado-div text-center">
    <h2>RESULTADO:</h2>
    <br>
    <div class="resultado text-center col-4">
      <h2>O resultado é <span>{{ props.resultado }}</span></h2>
    </div>
  </div>
</template>


<style scoped>
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
