<template>
  <p>{{props.name}}</p>
  <p>{{props.job}}</p>
  <p></p>
</template>
<script setup>
const props = defineProps({
  name: '',
  job: ''
})
</script>