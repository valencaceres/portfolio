<template>
  <div class="image">
    <div>
        <Navbar :sectionId="{ images: this.sectionId.images, text: this.sectionId.text, tech: this.sectionId.tech, contact: this.sectionId.contact }"/>
    </div>
    <h1 class="Title">Bienvenido</h1>
  </div>
</template>

<script>
import Navbar from './Navbar.vue';
export default {
name: 'Header',
components: {
    Navbar
},
props: {
    sectionId: {
      type: Object,
      required: true
    }
  },
}
</script>

<style>
.image{
  position: relative;
}
.image::before{
    background-image: url(../assets/images/fondoDev2.jpg);
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 100vh;
    content: "";
    opacity: 0.5;
    z-index: -1;
    display: flex;
    justify-content: center;
    align-items: center;
}
.Title{
    font-size: 3rem;
    text-shadow: 2rem black;
    position: absolute;
    top: 50%;
    left: 40%;
}
</style>