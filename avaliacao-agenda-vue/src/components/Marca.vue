<template>
  <div class="marca">
      <div class="contorno">
          <img src="../img/LogoAgenda.png" alt="Logo Agenda">
      </div>
      <span>Minha Agenda</span>
  </div>
</template>

<script>
export default {
    name: "Marca",
}
</script>

<style scoped>

    .marca{
        font-family: "negrito";
        padding: 40px;
        border-bottom: 2px solid var(--cor-destaque);
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: white ;
    }

    .contorno{
        background-color: white;
        padding: 20px 25px;
        border-radius: 50%;
        box-shadow: 1px 1px gray;
    }

    img{
        width: 40px;    
        vertical-align: middle;
    }

    span{
        margin-left: 10px;
        font-size: 250%;
        display: flex;
        align-items: center;
    }


   @media only screen and (max-width:600px){

       .marca{
           padding: 20px;
       }

       .contorno{
           padding: 15px 20px;
       }

       img{
           width: 40px;
       }

      span{
          font-size: 150%;
      }
   }

</style>