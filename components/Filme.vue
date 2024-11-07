<script setup>

//const params = useAttrs(); //pega uma variavel por vez
const params = defineProps(["filme", "alteraAlugado"]);// pega todo o objeto

</script>

<template>
 <div class="conteudo">
     <p>{{ params.filme.nome }}</p>
     <p v-if="params.filme.alugado == true" ><strong>Alugado</strong></p>
        <img src="https://via.placeholder.com/200"/>
        <p>{{ params.filme.price }}</p>
        <button  v-on:click="params.alteraAlugado(params.filme.id)" v-if="params.filme.alugado == false" >Alugar</button>
    </div>
</template>


<style scoped>

    .conteudo{
        display: flex;
        flex-direction: column;
        width: 200px;
        background-color: blueviolet;
        padding: 20px;
        color: white;
        gap: 10px;
        border-radius: 10px;
        text-align: center;
    }

    button{
        background-color: orange;
        width: 200px;
        color: white;
        height: 40px;
        border: none;
        cursor: pointer;
    }

</style>