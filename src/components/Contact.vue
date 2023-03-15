<template>
  <div class="container1">
    <div >
        <a class="linkedin" href="https://www.linkedin.com/in/valentin-caceres/"><Icon class="icon" icon="akar-icons:linkedin-fill" color="white" /></a>
        <a class="github" href="https://github.com/valencaceres"><Icon class="icon" icon="mdi:github" color="white" /></a>
        <a class="gmail" href="mailto:dev.vcaceres@gmail.com"><Icon class="icon" icon="logos:google-gmail" color="white" /></a>
    </div>
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
export default {
name: 'Contacto',
components:{
    Icon
}
}
</script>

<style>
.container1 {
  width: 25vw;
  height: 38vh;
  padding: 30px 0;
  background-color: #172757a1;
  display: flex;
  justify-content: center;
  border-radius: 1vh;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
}
.linkedin{
    background-color: #0e76a8;
    height: 10vh;
    width: 18vw;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 1vh;
    padding-top: 1.5vh;
    margin: 2vh 0;
}
.linkedin:hover{
    background-color: #0a5a80;
    transition: 0.2s ease-in-out;
}
.github{
    background-color: #000000;
    height: 10vh;
    width: 18vw;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 1vh;
    padding-top: 1.5vh;
    margin: 2vh 0;
}
.github:hover{
    background-color: #2e2e2e;
    transition: 0.2s ease-in-out;
}
.gmail{
    background-color: #ffffff;
    height: 10vh;
    width: 18vw;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 1vh;
    padding-top: 1.5vh;
    margin: 2vh 0;
}
.gmail:hover{
    background-color: #e6e6e6;
    transition: 0.2s ease-in-out;
}
</style>