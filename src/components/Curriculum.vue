<template>
  <div>
    <h2 class="curri">{{translate('cvMSJ')}} 
        <a  href="https://drive.google.com/file/d/1vW35kGmbsLoKz_72IZD_PCPvp5rBlYRZ/view?usp=share_link" download><Icon class="download" icon="material-symbols:download" color="white" /></a>
    </h2>
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
import es from '../es';
import en from '../en';
export default {
mixins: [es, en],
name: 'Curriculum',
components:{
    Icon
},
methods:{
    translate(prop){
      return this[this.lang][prop]
    }
  },
props:{
  lang: {
      type: String,
      required: true
    }
},
mounted(){
  console.log(this.lang);
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
@media (min-width: 320px) and (max-width:768px){
  .download{
    height: 13vh;
    width: 10vw;
  }
}
</style>