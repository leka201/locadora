<script setup>


const filmes = reactive([
  {
      id: 0,   
      nome:"Homem aranha no aranhaverso",
      price:"R$22,50",
      alugado: false,
  },
  {
      id: 1,
      nome:"Suzume",
      price:"R$22,50",
      alugado: false,
  },
  {
      id: 2,
      nome:"Avatar 2",
      price:"R$22,50",
      alugado: false,
  },
  {
      id: 3,
      nome:"His Dark Materials",
      price:"R$22,50",
      alugado: false,
  
    },
  {
      id: 4,
      nome:"Avatar 1",
      price:"R$22,50",
      alugado: false,
  },

])

function alteraAlugado(id){
  filmes[id].alugado = true;
}

</script>

<template>

  <Cabecalho/>
  <p><strong>Filmes recomendados:</strong></p>
    <div class="conteudo">

        <Filme v-for="filme in filmes" v-bind:filme="filme" v-bind:alteraAlugado="alteraAlugado"/>

    </div>
 
</template>


<style>

.conteudo{
  display: flex;
  gap: 30.78px;
}

</style>