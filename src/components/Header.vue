<template>
  <div class="image">
    <div>
        <Navbar :lang="lang"  :sectionId="{ images: this.sectionId.images, text: this.sectionId.text, tech: this.sectionId.tech, contact: this.sectionId.contact }"/>
    </div>
    <div class="titleContainer"><h1 :class="lang === 'es' ? 'Title' : 'titleEn'">{{translate('welcomeMSJ')}}</h1></div>
  </div>
</template>

<script>
import Navbar from './Navbar.vue';
import es from '../es';
import en from '../en';
export default {
mixins: [es, en],
name: 'Header',
components: {
    Navbar
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
  methods:{
    translate(prop){
      return this[this.lang][prop]
    }
  }
}
</script>

<style>
.titleContainer{
  width: 100%;
}
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
.titleEn{
  font-size: 3rem;
    text-shadow: 2rem black;
    position: absolute;
    top: 50%;
    left: 42%;
}
@media (min-width: 320px) and (max-width:768px) {
.image{
  width: 100%;
}
.Title{
  display: flex;
  align-items: center;
  font-size: 25px;
  justify-content: center;
  left: 30%;
}
.titleEn{
  font-size: 28px;
  left: 34%;
}
}
</style>