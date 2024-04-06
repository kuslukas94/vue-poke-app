<script setup>
import { ref } from 'vue'

//Stores whole pokemon list
const pokemon = ref();
//Stores information about Pokemons from the list
const pokemonSpecific = ref([]);

const getData = async () => {
	const res = await fetch("https://pokeapi.co/api/v2/pokemon?limit=12&offset=0");
	if (!res.ok) {
		throw new Error("Could not fetch data.");
	}
	const data = await res.json();

	pokemon.value = data.results;

	pokemon.value.forEach(async (element) => {
		const pokemonData = await fetch(element.url);

		const data = await pokemonData.json();
		pokemonSpecific.value.push(data);
		console.log(data);
		});
	}
getData();
</script>

<template>
  <div v-for="pokemon in pokemonSpecific" :key="pokemon.id" class="pokeSlot">
    <div class="pokeSpritesBlock">
		  <img :src="pokemon.sprites.other.showdown.front_default" alt="Pokemon Sprites" class="pokeSprites">
    </div>
		<h2 class="pokeName">{{ pokemon.name }}</h2>

			<h3 class="pokeId">#{{ pokemon.id }}</h3>	
		
			<h3 v-for="type in pokemon.types" :key="type.type.name" class="pokeType">
			{{ type.type.name }}
			</h3>
	</div>
</template>
