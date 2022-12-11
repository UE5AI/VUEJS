<template>
    <div> 
        <img v-bind:src="pic">
    </div> 
          
</template>

  
 
<script> 
  
import { ref } from 'vue'
export default {

    setup(){

        const pic = ref(require('@/images/racer.png'))

        return  { pic }
    }  

};
</script>

<style> 
     
</style>
