<template>
    
    <div class="container">
        <Background/>  
        <img class="clouds" src="@/images/BigClouds.png"> 
        <img class="MainLogo" src="@/images/MainLogo.svg"> 
        <p class="mainText">ОНИ ДОЛЖНЫ ЧТО-ТО ЗНАТЬ</p>
        <p class="lsMenu menuText" style="top: 6.5%;"><span>01</span></p>
        <p class="lsMenu menuText" style="top: 14.5%;"><span>02</span></p>
        <p class="lsMenu menuText" style="top: 22.5%;"><span>03</span> Подсказки</p>
        <p class="lsMenu menuText" style="top: 29.5%;"><span>04</span></p>
        <img class="lsMenu menuIcon" src="@/images/Menu.svg">  
        <img class="clouds" src="@/images/BigClouds.png">
        <p class="sdText"> {{scrollDownText}} </p>
        <img class="scrollDownImg" src="@/images/ScrollDown.svg">
        <p class="rsMenu"><a href = https://hd.kinopoisk.ru/>hd.kinopoisk.ru</a></p>
        <button class="searchPromo">
            <p>Искать промокод</p>
            <img src="@/images/ButtonArrow.svg">
        </button>  
    </div>   
 
</template>
 



<script>  
import Racer from "@/components/Racer.vue"
import Background from "@/components/Background.vue"     
 
export default {

    name: 'MainScene', 
    components: {
        Racer, Background,  
    },
    setup(){
 
    },

    data(){
        return{
            scrollDownText: "Скрольте вниз", 
        }
        
    }, 
    
};
 
</script>


<style>  

    .mainText{
    position: absolute;
    width: 100%;
    height: 20%;  
    align-self: center;
    top: 4%;
    z-index: 5;
    font-size: 3vw;
    font-family: "futura-bold";
    text-align: center;
    letter-spacing: -0.692308px;
    text-transform: uppercase;
    color: #FFCC64;
    }

    .container {   
    position: relative;
    display: flex;
    justify-content: center;  
    overflow: hidden; 
    } 

    .searchPromo {
    position: absolute;
    display: flex;
    width: 18%;
    height: 8%;
    left: 41%;
    top: 81%; 
    color: #333333;
    flex-direction: row; 
    background: #FFFFFF;
    box-shadow: 0px 5px 26px rgba(11, 75, 92, 0.0975713);
    border-radius: 8px;
    }

    .searchPromo:hover {
    background-color: rgb(253, 253, 47);
    }

    .searchPromo p {
    position: relative;
    font-size: 1vw; 
    align-self: center;
    margin-left: 20%;
    font-family: "kinopoisk-regular";
    }

    .searchPromo img {
    position: absolute;  
    align-self: center;
    width: 15%;
    height: 10%;
    margin-left: 70%;
    }

    .sdText {
    position: absolute;   
    font-size: 14px;
    font-size: 1vw;
    top: 72%; 
    left: -1.5%;
    z-index: 3;
    font-family: "kinopoisk-regular";
    transform: rotate(-90deg);
    }

    .scrollDownImg{
    position: absolute;  
    width: 0.42%;
    font-size: 1vw;
    top: 85.3%; 
    left: 1.8%;
    z-index: 3; 
    }

    .rsMenu {
    position: absolute; 
    font-size: 14px;
    font-size: 1vw;
    right:-1.7%;   
    top:46%;
    z-index: 3;  
    transform: rotate(90deg);
    }

    .lsMenu{ 
    left: 2.5%;
    z-index: 3;
    }

    .menuIcon {
    position: absolute;
    width: 1.6%; 
    top: 5%;
    }

    .menuText {
    position: absolute;   
    font-size: 14px; 
    font-size: 1vw;
    margin-top: 10%;
    word-spacing: 2em;
    text-decoration: underline;
    font-family: "kinopoisk-regular";
    text-underline-offset: 0.5em;
    color: #333333; 
    }


    .MainLogo{
    position: absolute;
    width: 13%; 
    top: 4%; 
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 3; 
    }

    span {  
    font-size: 1vw;
    font-family: "kinopoisk-medium"; 
    }
 
</style>