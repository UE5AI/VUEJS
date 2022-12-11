<template>
   
  <div class="app">
    <MainScene />
  </div>
  
  
</template>


<script> 
import MainScene from "./components/MainScene.vue"

export default {
  name: 'App',
  components: {
    MainScene
  }      
  
};
 
</script>




<style> 
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50; 
  }  

  @font-face {
    font-family: "futura-bold";
    src: url('~@/fonts/futura-bold.woff2');  
  }
  @font-face {  
    font-family: "kinopoisk-bold";
    src: url('~@/fonts/kinopoisk-bold.woff2'); 
  
  }
  @font-face {   
    font-family: "kinopoisk-light";
    src: url('~@/fonts/kinopoisk-light.woff2'); 
  
  }
  @font-face {   
    font-family: "kinopoisk-lite";
    src: url('~@/fonts/kinopoisk-lite.woff2'); 
  
  }
  @font-face {   
    font-family: "kinopoisk-medium";
    src: url('~@/fonts/kinopoisk-medium.woff2'); 
  
  }
  @font-face {   
    font-family: "kinopoisk-regular";
    src: url('~@/fonts/kinopoisk-regular.woff2'); 
  
  }
  @font-face {   
    font-family: "kinopoisk-semibold";
    src: url('~@/fonts/kinopoisk-semibold.woff2'); 
  
  }

  p {
  color: #333333;
  }
 
</style>
