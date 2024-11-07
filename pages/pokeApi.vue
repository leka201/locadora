<script setup>
import axios from 'axios';

let dados = ref()
let search = ref("")

 async function buscaTodos(){

    let resposta =  await axios.get("https://pokeapi.co/api/v2/pokemon/pikachu")
    console.log(resposta)
    dados.value = resposta.data


}

 async function Pesquisar(){

    let resposta =  await axios.get("https://pokeapi.co/api/v2/pokemon/" + search.value)
    console.log(resposta)
    dados.value = resposta.data

}

buscaTodos()

</script>

<template>

<h1>Consulta de Pokémon</h1>

<input v-model="search" >
<button v-on:click="Pesquisar()">Pesquisar</button>

<div v-if="dados != null">
<p>Nome: {{ dados.name }}</p>
<p>id: {{ dados.id }}</p>
<p>Habilidade:{{ dados.abilities[0].ability.name }}</p>
<img v-bind:src= "dados.sprites.front_default">
</div>

</template>