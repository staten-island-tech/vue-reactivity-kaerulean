<script setup>
import {ref} from 'vue'

const hunger = ref(100)
function minus(){
    hunger.value--
    console.log(hunger.value)
}
const down = setInterval(minus, 500);
const halt = ref(function stop(){
    clearInterval(down)
})

const foodSupply = ref(20)

const foods = [
    {
        name:"weeds",
        img: "/weed.jpg",
    },
    {
        name:"curry",
        img:"/curry.jpg",
    },
    {
        name:"tako sen[bai]",
        img:"/takosenbai.jpg",
    }
]

function plus(){
    const number = Math.floor(Math.random() * 30) + 10;
    hunger.value += number
}


function foodAdd(){
    foodSupply.value += Math.floor(Math.random() * 3) + 1;
}
setInterval(foodAdd, 9000)

function foodMinus(){
    foodSupply.value -= Math.floor(Math.random() * 3) + 1
}

</script>


<template>
    <!-- <p v-for="n in 10">{{ n }}</p> -->
    <p>hunger: {{ hunger }}</p>
    <p>food supply: {{ foodSupply }}</p>
    <p v-if="hunger === 0" :ref="halt">You lost!</p>
    <div class="container">
        <div v-for="food in foods" class="card">
            <h2>{{ food.name }}</h2>
            <img :src="food.img"> 
            <button disabled v-if="hunger === 0  || foodSupply <= 0">skill issue</button>
            <button v-else @click='plus(), foodMinus();'>eaet!</button>
        </div>
    </div>
</template>


<style scoped>
    img{
        border-style: solid;
        border-width: 0.1rem;
        width: 70%;
        height: 60%;
        visibility: visible;
    }

    .container{
    align-self: center;
    
    display: flex;
    flex-wrap: wrap;
    width: 90vw;
    background-color: #ffffff;
}

.card{
    height: 70vh;
    width: 33%;
    margin: 2.9rem 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    background-color: #006BA6;
    box-shadow: 5px 5px #ffffff;
}

h2{
    background-color: #ffffff;
    padding: 0.2rem;
}

</style>