<template>
  <div class="blocoContato">
      <div id="inicialContato">
        <span>{{contato.nome.charAt(0)}}</span>
      </div>

      <div class="descricaoContato">
        <span class="nomeInicial">{{contato.nome}}</span>

        <span>{{contato.telefone}}</span>
        <span>{{contato.email}}</span>
      </div>

      <button  @click="excluirContato(contato.id)" class="botaoRemover">
        <img src="../img/lixeira.png" alt="Remover Contato" />
      </button>
    </div>
</template>

<script>
import {mapActions} from "vuex";

export default {
    name: "BlocoContato",
    props: {
      contato: Object, 
    },
    methods: {
      ...mapActions(["excluirContato"]),
    }
}
</script>

<style>
.blocoContato {
  display: flex;
  border: 2px solid var(--cor-destaque);
  border-radius: 20px;
  font-family: "padrao";
  padding: 10px;
  margin-bottom: 10px;
  position: relative;
 
}

#inicialContato {
  background-color: var(--cor-destaque);
  padding: 20px 30px;
  border-radius: 50%;
  vertical-align: middle;
  color: white;
  font-size: 200%;
  font-family: "negrito";
}


.descricaoContato{
  margin-left:200px;
  float: right;
  text-align: right;
  width: 100%;
    
}
.descricaoContato span{
    display: block;
    font-size: 100%;
}

.nomeInicial{
    font-family: "negrito";
    font-size: 200% !important;
}

.botaoRemover {
  border: none;
  outline: none;
  width: 30px;
  height: 20px;
  background-color: white;
  text-align: right;
  margin: 50px 0px 0px 10px;
}

.botaoRemover:hover {
  cursor: pointer;
}

.botaoRemover img {
  width: 30px;
}

.botaoRemover img:active {
  filter: invert(100%);
}


@media only screen and (max-width:600px){
  .blocoContato{
    padding: 5px;
  }

  .nomeInicial{
    font-size: 100% !important;
  }

  .descricaoContato{
    margin-left: 10px;
  }

  .descricaoContato span{
    font-size: 80%;
}

  #inicialContato{
    padding: 20px 25px;
    font-size: 100%;

  }

  .botaoRemover{
    width: 25px;
    margin: 30px 0px 0px 0px;
  }

  .botaoRemover img {
    width: 25px;
  }


}


</style>