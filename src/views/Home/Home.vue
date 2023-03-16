<template>
  <div class="page">
    <div>
      <Header :lang="lang" :sectionId="{ images: 'images', text: 'text', tech: 'tech', contact:'contact' }"/>
      <select class="lang" name="lang" v-model="lang">
          <option value="es">Es</option>
          <option value="en">En</option>
      </select>
    </div>
    <div class="me">
  </div>
  <div class="about">
    <h2 class="aboutMe">{{translate('proyectMSJ')}}</h2>
  </div>
  <div id="images">
      <Images :lang="lang"/>
  </div>
  <div class="info">
    <div class="about1">
      <h2 class="aboutMe1">{{ translate('aboutMSJ') }}</h2>
    </div>
    <div class="textcont" id="text">
      <Text :lang="lang"/>
    </div>
  </div>
  <div class="info1">
    <div class="about1">
      <h2 class="aboutMe1">{{ translate('techMSJ') }}</h2>
    </div>
    <div class="tech" id="tech">
      <Technology/>
    </div>
  </div>
  <div class="info2">
    <div class="contact" id="contact">
      <Contact/>
    </div>
    <div class="about1">
      <h2 class="aboutMe1">{{translate('contactMSJ')}}</h2>
    </div>
  </div>
  <div class="cv">
    <Curriculum :lang="lang"/>
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
import es from '../../es';
import en from '../../en';
export default {
  mixins: [es, en],
  data(){
    return{
      lang: 'es'
    }
  },
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
    },
    translate(prop){
      return this[this.lang][prop]
    }
  },
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
.info2{
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
.lang{
  background-color: rgba(0, 0, 0, 0.432);
  position: absolute;
  top: 2%;
  right: 4%;
  border: none;
  height: 8vh;
  width: 4vw;
  border-radius: 1vh;
  outline: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  text-align: center;
  transition: width 0.2s ease-in-out, height 0.2s ease-in-out;
}
select option{
  background-color: rgb(22, 22, 22);
  transition: background-color 0.2s ease-in-out;
  height: 5vh;
}
select {
  /* quita el borde inferior */
  border-bottom: none;
  /* otros estilos para el select */
  font-size: 1rem;
  border: none;
  outline: none;
}
@media (min-width: 320px) and (max-width:768px) {
  .lang{
    background-color: rgba(0, 0, 0, 0.774);
    position: absolute;
    top: 1%;
    right: 3%;
    width: 15vw;
    -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  text-align: center;
  }
  .info{
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .about1{
    height: 20vh;
    margin: 5vh 0;
  }
  .about1 h2{
    font-size: 23px;
  }
  .textcont{
    width: 100%;
  }
  .info1{
    flex-direction: column;
    align-items: center;
    margin: 4vh 0;
  }
  .info2{
    flex-direction: column-reverse;
    align-items: center;
    margin: 4vh 0;
    height: 70vh;
    }
  .tech{
    width: 100%;
  }
  .contact{
    width: 100%;
  }
  select option{
    text-align: center;
    display: flex;
    align-items: center;
  }
}
</style>
