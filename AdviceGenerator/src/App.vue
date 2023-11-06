<script setup>
import HelloWorld from './components/HelloWorld.vue'


</script>

<template>
  <HelloWorld/>



  <div class="attribution">
            Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"> Frontend Mentor</a>. 
            Coded by <a href="https://github.com/BrayanGarzon/Advice-Generator.git" target="_blank"> DevDynasty</a>.
  </div>
  
  
</template>

<style scoped>
  .attribution {
    font-size: 15px;
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    color: white; /* Color de texto, ajusta según tus necesidades */
    padding: 10px; /* Espacio interno, ajusta según tus necesidades */
    display: flex;
    justify-content: center;
    align-items: center;
}
.attribution a{
  color: var(--color-neon-green);
}

/* Estilos específicos para pantallas pequeñas (Mobile: 375px o menor) */
@media screen and (max-width: 414px) {
  .attribution {
    width: 370px; 
    font-size: 10px;
  }


}

</style>
