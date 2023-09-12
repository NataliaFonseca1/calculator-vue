<script setup>
const props=defineProps([ "primeiroNumero",'segundoNumero', 'operacao'])
let operacaoSelecionada= ' ';
const emit=defineEmits(['realizar-operacao'])

function emitOperacao(event){
  emit('realizar-operacao', operacaoSelecionada);
}
</script>

<template>
  <form class="form-control text-center mt-3 pt-2">
    <input v-model="props.primeiroNumero"  type="number" class="p-1 m-2 fs-7" placeholder="Insira o primeiro número">
    <input v-model="props.segundoNumero" type="number" class="p-1 m-2 fs-7" placeholder="Insira o primeiro número">
    <div>
      <h2>Escolha a operação que deseja realizar:</h2>
    <select v-model="operacaoSelecionada"  @change="emitOperacao" class=" bg-gradien  mt-2 p-7">
  
    <option  value="somar">somar</option>
    <option  value="subtrair">Subtrair</option>
    <option  value="multiplicar">Multiplicar</option>
    <option  value="dividir">Dividir</option>
</select>
</div>
</form>

</template>