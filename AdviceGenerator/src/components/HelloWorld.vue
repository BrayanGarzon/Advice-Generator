<script>

import axios from 'axios';



export default {
  data() {
  return {
    advice: null,
  };
},

  methods: {
    async getAdvice() {
  try {
    const response = await axios.get('https://api.adviceslip.com/advice');
    console.log('Datos de la API:', response.data);

    if (response.data && response.data.slip) {
      this.advice = response.data.slip;
    } else {
      console.error('Datos inesperados en la respuesta de la API');
    }
  } catch (error) {
    console.error('Error al obtener el consejo', error);
  }
}


}


};

</script>

<template>


  <section>
    <div class="card">
      <div v-if="advice" class="tittle"><h4>ADVICE #{{ advice.id }}</h4></div>

      

      <div v-if="advice" class="text">{{ advice.advice }}</div>
      
      <div class="lineas">
        
        <img src="../assets/images/pattern-divider-desktop.svg" alt="">

      </div>
      
      <button @click="getAdvice" class="floating-button"><i class="fa-solid fa-dice-five"></i></button>

      
    </div>

  </section>
    
</template>

<style scoped>

  section{
    width: 100%;
    height: 100%;
  }

  section .card{
    width: 550px;
    height: 350px;
    background-color: var(--color-Dark-Grayish-Blue);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 30px; /* Añade el relleno que desees aquí */
    box-sizing: border-box; /* Mantén el tamaño total del elemento */
    gap: 5%;
    position: relative;
  }


  /*styles of the tittle*/

  section .card .tittle{
    width: 100%;
    height: 5%;
    text-align: center;
    color: var(--color-neon-green);
  }
  section .card .tittle h4{
    margin: 0;
    padding: 0;
    font-size: 14px;
    font-family: var(--font-family);
    letter-spacing: 4px;
  }

  /*styles of the text*/
  section .card .text{
    width: 100%;
    height: 70%;
    text-align: center;
    font-size: var(--font-size);
    font-weight: var(--font-wights);
    font-family: var(--font-family);
    color: var(--color-text);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  /*styles of the lineas*/
  section .card .lineas{
    width: 100%;
    height: calc(100% - 90%);
    display: flex;
    justify-content: center;
    align-items: center;
    
  }

  section .card .lineas img {
    max-width: 100%;
    height: auto;
  }




  /*styles of the button*/
  section .card button{
    height: 50px;
    width: 50px;
    border-radius: 50%;
    border: transparent;
    background-color: var(--color-neon-green);
    cursor: pointer;
  }
  section .card button i{
    font-size: 30px;
  }
  /* Estilos para la sombra cuando el puntero pasa sobre el botón */
  section .card button:hover {
    box-shadow: 0 0 25px hsl(150, 100%, 66%); /* Cambia el color de la sombra aquí */
  }

  .floating-button {
    position: absolute;
    bottom: -25px; /* Ajusta la posición vertical según tu preferencia */
    z-index: 1; /* Asegura que esté por encima del "card" */
    /* Estilos adicionales según tus preferencias */
  }

  



  


/* Estilos específicos para pantallas pequeñas (Mobile: 375px o menor) */
@media screen and (max-width: 414px) {
  section .card {
    width: 370px; /* Ajusta el ancho para pantallas pequeñas */
    /* Otros estilos específicos para pantallas pequeñas */
  }

  section .card .tittle h4 {
    font-size: 12px; /* Ajusta el tamaño de fuente para pantallas pequeñas */
    /* Otros estilos específicos para pantallas pequeñas */
  }
  /* Otros estilos específicos para pantallas pequeñas */
}
</style>
