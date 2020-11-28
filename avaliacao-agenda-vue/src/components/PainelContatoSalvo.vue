<template>
  <div v-if="todosContatos != 0" class="painelContatoSalvo" >
    <div class="title">Lista de Contatos</div>
    <BlocoContato
      v-for="contato in todosContatos"
      v-bind:key="contato.id"
      :contato="contato"
    />

  </div>
  <div class="mensagem" v-else> Nenhum Contato salvo na Agenda!</div>
</template>

<script>
import BlocoContato from './BlocoContato.vue'
import { mapGetters } from 'vuex';


export default {
  name: "PainelContatoSalvo",
  components: { BlocoContato
  },
  computed: mapGetters(["todosContatos"]),

};
</script>

<style>

.painelContatoSalvo{
    background-color:white;
    border-radius: 5px;
    padding: 20px;
    border: 2px solid white ;
    position: relative;
    left: 55%;
    top: 40px;
}

.title{
  font-size: 200%;
  font-family: "negrito";
  margin-bottom: 20px;
}

.mensagem{
  font-family: "negrito";
  font-size: 140%;
  margin: auto;
  background-color: white;
  padding: 20px;
  border-radius:5px ;
  border-bottom: 2px solid var(--cor-destaque);
  position: relative;
  left: 25%;
  top: 200px;
}

@media only screen and (max-width:600px){
  .painelContatoSalvo{
    padding: 10px;
    position: relative;
    top: 450px;
    left: auto;
    margin-bottom: 10px;
  }

  .title{
    font-size: 150%;
  }
  .mensagem{
    font-size: 120%;
    padding: 10px;
    text-align: center;
    position: relative;
    top: 450px;
    left: auto;
    margin-bottom: 10px;
  }
}


</style>