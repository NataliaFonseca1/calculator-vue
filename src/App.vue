<script setup>
import { reactive,transformVNodeArgs } from 'vue';

const estado= reactive({
primeiroNumero:'',
segundoNumero:'',
resultado:'',
operacao:" ",
})


function realizarOperacao(operacao){
switch(estado.operacao){
case 'somar':
estado.resultado = estado.primeiroNumero + estado.segundoNumero;
break
case 'subtrair':
estado.resultado = estado.primeiroNumero - estado.segundoNumero;
break
case 'multiplicar':
estado.resultado = estado.primeiroNumero * estado.segundoNumero;
break
case 'dividir':
estado.resultado = estado.primeiroNumero / estado.segundoNumero;
break
default:
estado.resultado=0;
}
}
</script>

<template>

<div class="container-md bg-info-subtle"  > 
  <header class="mt-2 mb-2 text-center">
  <h1>Calculadora Aritimética</h1>
</header>
  <form class="form-control text-center mt-3 pt-2">
    <input v-model="estado.primeiroNumero"  type="number" class="p-1 m-2 fs-7" placeholder="Insira o primeiro número">
    <input v-model="estado.segundoNumero" type="number" class="p-1 m-2 fs-7" placeholder="Insira o primeiro número">
    <div>
    <select v-model="estado.operacao" @click="realizarOperacao" class=" bg-gradien  mt-2 p-7" >
    <option  value="somar">somar</option>
    <option  value="subtrair">Subtrair</option>
    <option  value="multiplicar">Multiplicar</option>
    <option  value="dividir">Dividir</option>
    </select>
    
</div>
</form>

<h1 class="text-center m-2">{{estado.resultado}}</h1>
</div>
</template>



<style scoped>



</style>
