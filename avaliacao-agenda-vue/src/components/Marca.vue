<template>
  <div>
      <img src="../img/LogoAgenda.png" alt="Logo Agenda">
      <span>Minha Agenda</span>
  </div>
</template>

<script>
export default {
    name: "Marca",
}
</script>

<style scoped>

    div {
        background-color: white;
        font-family: "negrito";
        padding: 40px;
        border-bottom: 1px solid var(--cor-destaque);
    }

    img{
        width: 60px;
        vertical-align: middle;
        margin-right: 10px;
    }

    span{
        color: var(--cor-destaque);
        font-size: 250%;
        vertical-align: middle;
    }


   @media only screen and (max-width:600px){

       div{
           padding: 20px;
       }

       img{
           width: 40px;
       }

      span{
          font-size: 150%;
      }
   }

</style>