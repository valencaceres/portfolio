<template>
  <div class="page">
    <div>
      <Header :sectionId="{ images: 'images', text: 'text', tech: 'tech', contact:'contact' }"/>
    </div>
    <div class="me">
  </div>
  <div class="about">
    <h2 class="aboutMe">Mis Proyectos</h2>
  </div>
  <div id="images">
      <Images/>
  </div>
  <div class="info">
    <div class="about1">
      <h2 class="aboutMe1">Sobre Mi</h2>
    </div>
    <div class="textcont" id="text">
      <Text/>
    </div>
  </div>
  <div class="info1">
    <div class="about1">
      <h2 class="aboutMe1">Tecnologias</h2>
    </div>
    <div class="tech" id="tech">
      <Technology/>
    </div>
  </div>
  <div class="info1">
    <div class="contact" id="contact">
      <Contact/>
    </div>
    <div class="about1">
      <h2 class="aboutMe1">Contacto</h2>
    </div>
  </div>
  <div class="cv">
    <Curriculum/>
  </div>
  </div>

</template>

<script>
import Images from '../../components/Images.vue';
import Text from '../../components/Text.vue';
import Header from '../../components/Header.vue';
import Technology from '../../components/Technology.vue';
import Contact from '../../components/Contact.vue';
import Curriculum from '../../components/Curriculum.vue';
export default {
  name: "Home",
  components: {
    Images,
    Text,
    Header,
    Technology,
    Contact,
    Curriculum
  },
  mounted() {
    this.scrollToSection();
  },
  methods: {
    scrollToSection() {
      let hash = window.location.hash;
      if (hash) {
        let element = document.querySelector(hash);
        if (element) {
          element.scrollIntoView({ behavior: 'smooth' });
        }
      }
    }
  }
};
</script>

<style>
.page{
  width:100%;
}
.me {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
}
.about{
  margin: 3vh 0 4vh 0;
  width: 100%;
  height: 5vh;
  display: flex;
  justify-content: center;
  width: 100%;
}
.aboutMe{
  width: 80%;
  text-align: center;
  border-bottom: 1px solid white;
}
.info{
  display: flex;
  flex-direction: row-reverse;
  width: 100%;
  justify-content: space-around;
  margin-top: 5vh;
}
.about1 {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #fff;
  position: relative;
  width: 50%;
}

.about1 h2 {
  font-size: 40px;
  font-weight: 700;
  text-transform: uppercase;
  margin: 0;
  position: relative;
}

.about1 h2::before,
.about1 h2::after {
  content: "";
  position: absolute;
  border: 1px solid white;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-iteration-count: infinite;
}

.about1 h2::before {
  top: 0;
  left: 0;
  width: 0;
  animation-name: line-top;
}

.about1 h2::after {
  bottom: 0;
  right: 0;
  width: 0;
  animation-name: line-bottom;
}

@keyframes line-top {
  0% {
    width: 0;
    left: 0;
  }
  50% {
    width: 100%;
    left: 0;
  }
  100% {
    width: 0;
    left: 100%;
  }
}

@keyframes line-bottom {
  0% {
    width: 0;
    right: 0;
  }
  50% {
    width: 100%;
    right: 0;
  }
  100% {
    width: 0;
    right: 100%;
  }
}
.aboutMe1{
  width: 30vw;
  text-align: center;
  height: 10vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.info1{
  display: flex;
  width: 100%;
  justify-content: space-between;
  height: 50vh;
}
.left{
  margin-left: 5vw;
}
.contact{
  width: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.tech{
  width: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.textcont{
  width: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.cv{
  height: 15vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
