<template>

  <div>
    <Marca />
  </div>

  <div id="container">
      <PainelContato />
      <PainelContatoSalvo />
  </div>

</template>

<script>
import PainelContatoSalvo from './components/PainelContatoSalvo.vue'
import PainelContato from './components/PainelContato.vue'
import Marca from './components/Marca.vue'


export default {
  name: 'App',
 components: { Marca, PainelContato, PainelContatoSalvo}
};
</script>

<style>
:root {
  --cor-destaque: #0707ffff ;
}

@font-face {
  font-family: "padrao";
  src: url(./fonts/Ubuntu-Regular.ttf);
}

@font-face {
  font-family: "negrito";
  src: url(./fonts/Ubuntu-Bold.ttf);
}

body {
  margin: 0;
  background-color: #dddddd;
}

#container {
  display: flex;
  padding: 20px;
}

/* .entrada {
  color: #22a7f0;
}

.gasto {
  color: red;
}  */

@media only screen and (max-width:600px){
  #container{
    display: block;
    padding: 10px;
  }
}
</style>
