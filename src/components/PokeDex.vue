<script setup>
import { ref } from 'vue'

const pokemon = ref()


//FETCH DATA FROM POKEAPI
fetchData();

async function fetchData(){
    try{
        const response = await fetch('https://pokeapi.co/api/v2/pokemon/');
        if(!response.ok){
            throw new Error("Could not fetch resource");
        }
        const pokemon = await response.json();
        console.log(pokemon);
    }
    catch(error){
        console.error(error);
    }
}
</script>

<template>
	<div v-for="item in pokemon" :key="item.name">
		<h2>{{ item.name }}</h2>
	</div>
</template>