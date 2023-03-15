<template>
<div class="compCont">
  <div class="imgcontainer">
    <a class="blackout" href="https://github.com/valencaceres/minga-front">
      <img class="img" src="../assets/images/minga.png" alt="" />
        <h3 class="img-title">Minga</h3>
    </a>
    <a class="blackout" href="https://github.com/valencaceres/vinland-front">
      <img class="img" src="../assets/images/Vinland.png" alt="" />
        <h3 class="img-title2">Vinland</h3>
    </a>
    <a class="blackout" href="https://github.com/valencaceres/Challenge-Petshop">
      <img class="img" src="../assets/images/Petshop.png" alt="" />
        <h3 class="img-title3">Petshop</h3>
    </a>
  </div>
</div>
</template>

<script>
export default {
name: 'Images',
}
</script>

<style>
.compCont{
  display: flex;
  justify-content: center;

}
.imgcontainer {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 98%;
  height: 34vh;
  position: relative;
  border-radius: 1vh;
}
.img {
  height: 25vh;
  border-radius: 1vh;
  transition: 0.2s ease-in-out;
  margin-right: 1rem; /* Agrega un margen derecho a todas las imágenes */
  opacity: 0.5;
}

.img:last-child {
  margin-right: 0; /* Elimina el margen derecho de la última imagen en la fila */
}

.img:hover{
  transform: scale(1.2);
  opacity: 1;
}
.blackout{
  transition: 0.3 ease-in-out;
}
.blackout:hover > .img-title{
  opacity: 0 !important;
}
.blackout:hover > .img-title2{
  opacity: 0 !important;
}
.blackout:hover > .img-title3{
  opacity: 0 !important;
}
.img-title{
  position: absolute;
  top: 40%;
  left: 12%;
  transition: opacity 0.3s ease-in-out;
  font-size: 2rem;
}
.img-title2{
  position: absolute;
  top: 40%;
  left: 45%;
  transition: opacity 0.3s ease-in-out;
  font-size: 2rem;
}
.img-title3{
  position: absolute;
  top: 40%;
  left: 78%;
  transition: opacity 0.3s ease-in-out;
  font-size: 2rem;
}
</style>