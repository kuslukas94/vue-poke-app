<script setup>
import { ref } from 'vue'

// Pikachu evolution list
const pikachuevo = ref([
    { evo: 'Pikachu' },
    { evo: 'Raichu' },
    { evo: 'Pichu'},
    ])

//FETCH DATA FROM POKEAPI
fetch("https://pokeapi.co/api/v2/pokemon/raichu")
    .then(response => {

        if(!response.ok){
            throw new Error("Could not fetch resource");
        }
        return response.json();
    })
    .then(data => console.log(data))
    .catch(error => console.error(error))
</script>

<template>
	<ul v-for="(item) in pikachuevo">
  	{{ item.evo }}
	</ul>
</template>