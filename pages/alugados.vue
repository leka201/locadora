<script setup>

const categorias = [
    {nome:"Ação"},
    {nome:"Suspense"},
    {nome:"Terrror"},
    {nome:"Dorama"},
    {nome:"Comédia"},
    {nome:"Anime"},
]

</script>

<template>

    <h1>Categorias de filmes</h1>
    <div v-for="categoria in categorias">
        <p>{{ categoria.nome }}</p>
    </div>

</template>