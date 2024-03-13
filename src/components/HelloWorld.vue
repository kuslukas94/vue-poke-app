<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Dejve, dotaz: VUE neznám a text edituju v HelloWorld.vue - je to dáno šablonou a reálně bych si to měl promazat a psát to do App.vue nebo to takto mám nechat? Působí to na mě krkolomně, ale chápu, že to může mít význam.<br>
      Například právě nadpis Hello Světe je definovaný dost složitě. Nestačila by html h1 a nastylovat?<br>
      Ptám se z toho důvodu, abych věděl, jestli přemýšlím správně nebo zatím ještě s přemýšlením mám počkat. :D
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
