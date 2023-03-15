<template>
<div class="text-container">
  <p class="text">
    Soy un desarrollador web full stack certificado en MERN, Mobile y con conocimientos en Vue.js (De hecho este portfolio esta creado con Vue).
    Puedo destacar de mi persona mi capacidad para tomar el papel de líder si la situación lo requiere, además de mi gran carisma que hace que mi relación con mis compañeros/as de trabajo y allegados sea la mejor, sumado a mi competitividad, que hace que siempre busque mejorar.
    Puedes seguir navegando por mi pagina web o visitar mis repositorios, en los que podras encontrar algunos de mis proyectos!
  </p>
  <div class="line"></div>
</div>
</template>

<script>
export default {
name: 'Text',
}
</script>

<style>
.text-container {
  width: 65%;
  padding: 30px 0;
  background-color: #172757a1;
  display: flex;
  justify-content: center;
  border-radius: 1vh;
}

.text {
  color: white;
  font-size: 20px;
  line-height: 30px;
  text-align: justify;
  width: 80%;
  height: 30vh;
  overflow: auto;
  transition: width 0.5s ease-in-out;
}
.text::-webkit-scrollbar{
  width: 10px;
  background-color: transparent;
  transition: all 0.5s ease-in-out;
}
.text::-webkit-scrollbar-thumb {
  background-color: transparent;
  border-radius: 5px;
}
.text::-webkit-scrollbar-track {
  background-color: transparent;
}
.text:hover::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, 0.5);
  border-radius: 5px;
  transition: all 0.5s ease-in-out;
}
</style>


<!-- Soy un desarrollador web full stack certificado en MERN, Mobile y con conocimientos en Vue.js (De hecho este portfolio esta creado con Vue).
Puedo destacar de mi persona mi capacidad para tomar el papel de líder si la situación lo requiere, además de mi gran carisma que hace que mi relación con mis compañeros/as de trabajo y allegados sea la mejor, sumado a mi competitividad, que hace que siempre busque mejorar.
Puedes seguir navegando por mi pagina web o visitar mis repositorios, en los que podras encontrar algunos de mis proyectos! -->