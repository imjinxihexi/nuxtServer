<template>
 <div class="nx-main-wrap">
      <top-bar></top-bar>
      <!-- <left-nav></left-nav>
      <contact-bar ></contact-bar>  -->
      <keep-alive>
        <nuxt-child class="nx-main-content"/> 
      </keep-alive>
      <tab-bar class="tab-bar" @tabChange ="tabChange"></tab-bar>

 </div>
</template>


<script>
import TopBar from '~/components/TopBar';
import BottomBar from '~/components/BottomBar';
import TabBar from '~/components/TabBar';
import LeftNav from '~/components/LeftNav';
import ContactBar from '~/components/ContactBar';
 export default {
   data () {
     return {

     }
   },
   methods: {
     tabChange(curValue){
       switch (curValue) {
         case 2:
             this.$router.push({path:'/home/welcome/cart'});
           break;
         case 3:
             this.$router.push({path:'/home/welcome/user'});
           break;
         default:
           break;
       }
       
     }
   },
   components:{
     TopBar,
     TabBar,
     BottomBar,
     LeftNav,
     ContactBar,
   }
 } 
</script>

<style lang="scss">
  .nx-main-wrap {
    position: relative;
    height: 100%;

    .nx-main-content {
      text-align: center;
    }

    .tab-bar {
      position: absolute;
      color: white;
      width: 100%;
      height: 48px;
      line-height: 48px;
      background: #41B883;
      text-align: center;
      bottom: 0;
      left: 0;
    }
  }
 
</style>
<style>
  body, html, #__nuxt, #__layout, #__layout>div {
    height: 100%;
  }
</style>
