<script setup>

import JordanJob from "./components/jobs/JordanJob.vue";
import OgabekJob from "./components/jobs/OgabekJob.vue";
import {computed, ref, watch} from "vue";


let count = ref(0);

watch(count, (newValue, oldValue) => {
  console.log(`Eski qiymat: ${oldValue}`)
  console.log(`Yangi qiymat: ${newValue}`)

  if (count.value >= 10) {
    alert("limitga yetdingiz")
    return count.value = 10;
  }else if (count.value <= 0) {
    alert("limit tugadi")
    return count.value = 0;
  }
})

function add (){
  count.value++
}

function remove (){
  count.value--;
}

let name = ref('')
let sureName = ref('')

let fish = computed(() => {
  return name.value + ' ' + sureName.value
})

let isTrue = ref(true)
let div = ref('')

watch(div, () => {
  if (div.value === 'uchir') {
    isTrue.value = false
  }else {
    isTrue.value = true
  }
})
</script>

<template>
  <JordanJob name="Jovohir" job="gamer"/>
  <OgabekJob name="Ogabek" job="mexanick"/>


  <div>
    <div>
      <button @click="add">+</button>
      <span>{{count}}</span>
      <input v-if="isTrue" type="text" v-model="div" placeholder="kalit suz kirit">
      <button @click="remove">-</button>
    </div>
  </div>


  <p class="text-white">{{fish}}</p>

    <input class="mr-[20px]" type="text" v-model="name">
    <input type="text" v-model="sureName">
</template>


<style scoped>

</style>
