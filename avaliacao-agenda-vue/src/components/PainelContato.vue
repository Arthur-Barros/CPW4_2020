<template>
  <div class="formularioContato">
    <form @submit="salvar">
      <label for="nome">Nome</label>
      <input type="text" id="nome" name="nome" v-model="nome" required />
      <label for="telefone">Telefone</label>
      <input
        type="tel"
        id="telefone"
        name="telefone"
        v-mask="['(##) ####-####', '(##) #####-####']"
        v-model="telefone"
        required
      />
      <label for="email">E-mail</label>
      <input type="email" id="email" name="email" v-model="email" />

      <button>Salvar</button>
    </form>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import Contato from "../models/Contato";
import { mask } from "vue-the-mask";

export default {
  name: "PainelContato",
  data: () => {
    return {
      nome: "",
      telefone: "",
      email: "",
    };
  },
  methods: {
    ...mapActions(["salvarContato"]),
    salvar(event) {
      event.preventDefault();

      const contato = new Contato(this.nome, this.telefone, this.email);
      this.salvarContato(contato);
      this.limparFormulario();
    },
    limparFormulario() {
      this.nome = "";
      this.telefone = "";
      this.email = "";
    },
  },
  directives: { mask },
};
</script>

<style scoped>

.formularioContato {
  margin: 40px auto auto auto;
  border-radius:5px;
  font-family: "padrao";
  padding: 20px;
  width: 40%;
  background-color: white;
  position: absolute;
}

label,
input {
  margin-top: 10px;
}

label {
  font-size: 130%;
  font-family: "negrito";
}

#nome,
#telefone,
#email {
  display: block;
  margin-bottom: 20px;
  padding: 10px;
  border-radius: 5px;
  outline: none;
  font-size: 100%;
  border: none;
  color: var(--cor-destaque);
  width: 50%;
  border: 2px solid var(--cor-destaque);
}

button {
  margin-top: 20px;
  cursor: pointer;
  background-color: var(--cor-destaque);
  border: none;
  outline: none;
  border-radius: 5px;
  padding: 15px 20px;
  color: white;
  font-family: "negrito";
  font-size: 120%;
}

@media only screen and (max-width: 600px) {
 
  .formularioContato {
    width: 80%;
    position: absolute;
  }

  #nome,
  #telefone,
  #email {
    width: 80%;
    font-size: 90%;
  }
}
</style>