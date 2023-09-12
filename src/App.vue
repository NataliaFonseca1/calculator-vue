<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue'
  import Formulario from './components/Formulario.vue'
  import Resultado from './components/Resultado.vue'

const estado= reactive({
primeiroNumero:" ",
segundoNumero:" ",
resultado:" ",

})


function realizarOperacao(operacao){
switch(operacao){
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
  <Cabecalho/>
<Formulario @realizar-operacao="realizarOperacao" :primeiro-numero="estado.primeiroNumero" :segundo-numero="estado.segundoNumero"/>
<Resultado :resultado="estado.resultado"/>
</div>
</template>


<style scoped>



</style>
