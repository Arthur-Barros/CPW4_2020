<template>
  <div v-if="todosContatos != 0" class="painelContatoSalvo" >
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
    background-color: rgb(96, 96, 255);
    border-radius: 5px;
    padding: 20px;
    margin: 40px auto auto auto;
    border: 2px solid var(--cor-destaque) ;
}

.mensagem{
  
  font-family: "negrito";
  font-size: 140%;
  margin: auto;
  background-color: white;
  padding: 20px;
  border-radius:5px ;
  border-bottom: 2px solid var(--cor-destaque);
}

@media only screen and (max-width:600px){
  .painelContatoSalvo{
    padding: 10px;
    
  }

  .mensagem{
    font-size: 120%;
    padding: 10px;
    text-align: center;
  }
}


</style>