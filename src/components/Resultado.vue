<script setup>
  const props = defineProps([ 'resultado'])
</script>


<template>
  <h1 class="text-center m-2">{{props.resultado}}</h1>
</template>