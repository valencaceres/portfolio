<template>
  <div class="logo">
    <p>Valentin Caceres</p>
  </div>
  <div class="navlist" :class="{ 'desplegable': !desplegado }">
    <button v-if="showNavbarButton" class="boton-desplegable" @click="desplegarMenu"><Icon class="icon" icon="ei:navicon" color="white" /></button>
    <ul>
        <a class="nav-link" @click="scrollToSection(sectionId.images)">{{translate('nav1')}}</a>
        <a class="nav-link" @click="scrollToSection(sectionId.text)">{{translate('nav2')}}</a>
        <a class="nav-link" @click="scrollToSection(sectionId.tech)">{{translate('nav3')}}</a>
        <a class="nav-link" @click="scrollToSection(sectionId.contact)">{{translate('nav4')}}</a>
    </ul>
  </div>
</template>

<script>
import VueScrollTo from 'vue-scrollto';
import es from '../es';
import en from '../en';
import { Icon } from '@iconify/vue';
export default {
mixins: [es, en],
name: 'Header',
name: 'Navbar',
data() {
    return {
      desplegado: false,
      showNavbarButton: false,
      navlist: 0,
    }
  },
components:{
  Icon
},
props: {
    sectionId: {
      type: Object,
      required: true
    },
    lang: {
      type: String,
      required: true
    }
  },
  mounted() {
    console.log(this.sectionId.images);
    console.log(this.sectionId.text);
    console.log(window.innerWidth);
    if ( window.innerWidth >= 320 && window.innerWidth <= 768) {
      this.showNavbarButton = true;
      this.navlist = window.innerHeight + 'px';
    }
  },
  methods: {
    scrollToSection(sectionName) {
      VueScrollTo.scrollTo(`#${sectionName}`, 500, {
        easing: 'ease-in-out',
      });
    },
    translate(prop){
      return this[this.lang][prop]
    },
    desplegarMenu() {
      this.desplegado = this.desplegado ? false : true;
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
.boton-desplegable{
  display: none;
}
@media (max-width: 768px) {
  .logo{
    display: flex;
    font-size: 20px;
    width: 100%;
    height: 15vh;
    align-items: start;
    justify-content: center !important;;
    margin: 0 5vw 0 0;
  }
  .logo p{
    width: 100%;
    text-align: center;
    margin-right: 5vw;
  }
  ul{
    display: flex;
    flex-direction: column;
    width: 100%;
    position: fixed;
    background-color: black;
    top: 0;
    height: 100vh;
    width: 100%;
    padding: 10vh 0;
    z-index: 10;
    transition: transform 0.3s ease, opacity 0.3s ease;
    transform: translateX(100);
  }
  .navlist {
    position: fixed;
    left: 0;
    top: 0;
    z-index: 15;
  }
  .boton-desplegable{
    display: inline;
    padding: 0;
    background-color: transparent;
    border: 1px solid transparent;
    position: fixed;
    z-index: 20;
}
  .desplegable ul {
    display: none;
  }
  .desplegable ul.desplegado {
    position: absolute;
    right: 0;
    transform: translateX(0);
  }
  .nav-link{
    margin: 2vh 0 2vh 2vw;
    width: 40%;
  }
}
</style>