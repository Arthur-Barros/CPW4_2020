<template>

<div id="painelContato">
        <div id="formularioContato">

            <form @submit="salvar">

                <label for="nome">Nome</label>
                <input type="text" id="nome" name="nome"  v-model="nome" required>
                <label for="telefone">Telefone</label>
                <input type="text" id="telefone" name="telefone" v-model="telefone" required>
                <label for="email">E-mail</label>
                <input type="email" id="email" name="email" v-model="email" >

                <button>Salvar</button>
            </form>
        </div>
</div>
</template>

<script>

import { mapActions } from 'vuex';
import Contato from "../models/Contato";

export default {
    name: "PainelContato",
    data: () => {
        return {
            nome: "",
            telefone: "",
            email: "",
        }
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
        }
    },
}
</script>

<style scoped>

#painelContato{
    width: 50%;
    padding: 20px;
}

#formularioContato{
    border-radius: 20px;
    font-family: "padrao";
    padding: 20px;
}

label, input{
    margin-top: 10px;
}

label{
    font-size: 130%;
    font-family: "negrito";
}

#nome, #telefone, #email{
    display: block;
    margin-bottom: 20px;
    padding: 10px;
    border-radius: 5px;
    outline: none;
    font-size: 100%;
    border: none;
    color: var(--cor-destaque);
    width: 40%;
    border-bottom: 2px solid var(--cor-destaque);
}

button{
    margin-top: 20px;
    cursor: pointer;
    background-color: var(--cor-destaque);
    border: none;
    outline: none;
    border-radius: 5px;
    padding: 15px 20px;
    color: white;
    font-family: "negrito";
    font-size: 110%;
}

@media only screen and (max-width:600px){
    #painelContato{
        width: 100%;
        padding: 40px 5px;
    }
    #formularioContato{
        padding: 5px;
    }

    #nome, #telefone, #email{
        width: 80%;
        font-size: 90%;
    }

    
}

</style>