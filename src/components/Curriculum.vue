<template>
  <div>
    <h2 class="curri">Descarga mi CV 
        <a  href="https://drive.google.com/file/d/1vW35kGmbsLoKz_72IZD_PCPvp5rBlYRZ/view?usp=share_link" download><Icon class="download" icon="material-symbols:download" color="white" /></a>
    </h2>
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
export default {
name: 'Curriculum',
components:{
    Icon
}
}
</script>

<style>
.download{
    width: 4vw;
    height: 8vh;
}
.curri{
    display: flex;
    align-items: center;
}
</style>