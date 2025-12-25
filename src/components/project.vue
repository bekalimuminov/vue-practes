<template>
<p>fgbhn</p>
</template>

<script setup>
   async function data (){
     let res = await fetch("http://localhost:3000/api/testREST")
     let data = await res.json()
     console.log(data)
   }
   data()
</script>