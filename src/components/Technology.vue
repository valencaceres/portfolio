<template>
  <div class="container">
    <Icon class="icon" icon="skill-icons:react-dark" />
    <Icon class="icon" icon="skill-icons:mongodb" />
    <Icon class="icon" icon="skill-icons:expressjs-dark" />
    <Icon class="icon" icon="skill-icons:nodejs-dark" />
    <Icon class="icon" icon="skill-icons:javascript" />
    <Icon class="icon" icon="skill-icons:css" />
    <Icon class="icon" icon="skill-icons:html" />
    <Icon class="icon" icon="mdi:git" color="red" />
    <Icon class="icon" icon="ion:logo-github" />
    <Icon class="icon" icon="vscode-icons:file-type-vue" />
    <Icon class="icon" icon="skill-icons:postman" />
    <Icon class="icon" icon="skill-icons:redux" />
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
export default {
name: 'Technology',
components: {
		Icon,
	},
}
</script>

<style>
.container {
  width: 30vw;
  height: 35vh;
  padding: 30px 0;
  background-color: #172757a1;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 1vh;
  overflow: auto;
  flex-wrap: wrap;
}
.icon{
    width: 5vw;
    height: 8vh;
    margin-bottom: 2vh;
}
.container::-webkit-scrollbar{
  width: 10px;
  background-color: transparent;
  transition: all 0.5s ease-in-out;
}
.container::-webkit-scrollbar-thumb {
  background-color: transparent;
  border-radius: 5px;
}
.container::-webkit-scrollbar-track {
  background-color: transparent;
}
.container:hover::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, 0.5);
  border-radius: 5px;
  transition: all 0.5s ease-in-out;
}
@media (min-width: 320px) and (max-width:768px){
  .container{
    width: 80%;
  }
  .icon{
    height: 20%;
    width: 15vw;
  }
}
</style>