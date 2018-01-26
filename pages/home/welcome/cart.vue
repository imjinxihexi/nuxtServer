<template>
 <div>
     我是购物车 {{count}}
 </div>
</template>

<script>
 export default {
   data () {
     return {
        count:0,
     }
   },
   mounted(){
    const _this = this;
     setInterval(()=>{
         this.count ++;
     },100);
   },
   created(){
    
   },
   methods: {
       
   },
   
 }
</script>

<style lang="scss" scoped>

 
</style>
