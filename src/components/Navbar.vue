<template>
  <div class="logo">
    <p>Valentin Caceres</p>
  </div>
  <div class="navlist">
    <ul>
        <a class="nav-link" @click="scrollToSection(sectionId.images)">Proyectos</a>
        <a class="nav-link" @click="scrollToSection(sectionId.text)">Sobre Mi</a>
        <a class="nav-link" @click="scrollToSection(sectionId.tech)">Tecnologias</a>
        <a class="nav-link" @click="scrollToSection(sectionId.contact)">Contacto</a>
    </ul>
  </div>
</template>

<script>
import VueScrollTo from 'vue-scrollto';
export default {
name: 'Navbar',
props: {
    sectionId: {
      type: Object,
      required: true
    }
  },
  mounted() {
    console.log(this.sectionId.images);
    console.log(this.sectionId.text);
  },
  methods: {
    scrollToSection(sectionName) {
      VueScrollTo.scrollTo(`#${sectionName}`, 500, {
        easing: 'ease-in-out',
      });
    },
  },
}
</script>

<style>
.logo {
  font-size: 30px;
  font-family: Montserrat, sans-serif;
  position: absolute;
  top: 3%;
  left: 5%;
  display: inline-block;
  font-weight: 650;
}
.logo p {
  display: inline-block;
  position: relative;
}
.logo p::before {
  content: "";
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 0%;
  height: 2px;
  background-color: #ffffff;
  transition: width 0.3s ease-in-out;
}
.logo p::after {
  content: "";
  position: absolute;
  top: -3px;
  right: 0;
  width: 0%;
  height: 2px;
  background-color: #ffffff;
  transition: width 0.3s ease-in-out;
}
.logo p:hover::before {
  width: 100%;
}

.logo p:hover::after {
  width: 100%;
}

.logo p:hover {
  transition: transform 0.3s ease-in-out;
  transform: scale(1.1);
}
.navlist{
  position: absolute;
  top: 4%;
  right: 10%;
}
.nav-link {
  position: relative;
  width: 5vw;
  margin: 0 2vw 0 2vw;
  font-weight: 600;
  font-size: 20px;
}

.nav-link::before {
  content: "";
  position: absolute;
  bottom: -5px;
  left: 50%;
  transform: translateX(-50%) scaleX(0);
  transform-origin: center; 
  width: 100%;
  height: 2px;
  background-color: rgb(250, 250, 250);
  transition: transform 0.2s;
}

.nav-link:hover::before {
  transform: translateX(-50%) scaleX(1);
}
</style>