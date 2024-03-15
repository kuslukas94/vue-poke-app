<script setup>
import { ref } from 'vue'

const pikachuevo = ref([{ evo: 'Pikachu' }, { evo: 'Raichu' }, { evo: 'Pichu'}])
</script>

<template>
	<ul v-for="(item) in pikachuevo">
  	{{ item.evo }}
	</ul>
</template>