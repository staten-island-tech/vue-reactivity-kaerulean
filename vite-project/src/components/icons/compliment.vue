<script setup>
import { ref } from 'vue'

const count = ref(0)

const showImage = ref(true)

function insertImage(){
  console.log("HI")
  showImage.value = ! showImage.value
}
</script>

<template>
  <div class="box">
    <button @click="count++; insertImage()">call her weird (she likes it)</button>
    <h2>weird counter: {{ count }}</h2>
    <img v-if="showImage === true" :class="{ imgTrue: showImage }" src='/ryoblush.jpg' alt="" />
    <img v-else class="imgElse" src='/ryoyay.jpg' alt="" /> 
  </div>
</template>


<style scoped>
button{
  font-size: 1 rem;
}
.imgTrue{
  visibility: visible;
  height: 1 rem;
  width: 22%;
  border-style: solid;
  border-width: 0.1rem;
}
.imgElse{
  visibility: visible;
  border-style: solid;
  border-width: 0.1rem;
  height: 15rem;
}

</style>