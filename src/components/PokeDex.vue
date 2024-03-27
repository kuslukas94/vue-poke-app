<script setup>
import { ref } from 'vue'

const pokemon = ref();
const pokemonSpecific = ref([]);
const pokemonType = ref([]);

const getData = async () => {
	const res = await fetch("https://pokeapi.co/api/v2/pokemon?limit=5&offset=0");
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
	<div v-for="item in pokemonSpecific" :key="item.name">
		<h2>{{ item.name }}</h2>
	</div>
</template>