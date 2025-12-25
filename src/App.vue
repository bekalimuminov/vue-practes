<script setup>
   import {ref} from "vue";

   let count = ref(0);
   function add (){
     if (count.value < 10){
       count.value++;
     }
   }
   function remove (){
     if (count.value > 0){
       count.value--;
     }
   }
   let key = ref("")
</script>

<template>
<div :class="key === 'uchir' ? 'hidden' : ''">
  <button @click="remove">-</button>
  <input type="number" v-model="count">
  <button @click="add">+</button>
</div>
  <input class="border border-red-500 rounded-[5px] py-[5px] px-[5px]" placeholder="yashirin suz kirit" type="text" v-model="key">
</template>

<style scoped>

</style>
