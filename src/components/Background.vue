<template> 
    <img class="bgImage" v-bind:src="pic"> 

    <div class="rectLG"></div>

    <button @click="next" class="next">
        <img class="buttonArrow" src="@/images/ButtonArrow.svg"> 
    </button >

    <div class="sliderCount">
        <p>{{(this.visibleSlide + 1)}}/{{this.slidesLen}}</p>
    </div>
    
    <div class="slider"> 
        <carousel
        @next="next"
        @prev="prev">
            <carousel-slide v-for="(slide, index) in slides" 
                :key="slide" 
                :index="index"
                :visibleSlide="visibleSlide"> 
                <img class="sliderImage" v-bind:src="slide.image_path">
                 
            </carousel-slide> 
        </carousel>   
    </div>
    <div class="sliderTextContainer">
        <p v-text="this.slidesText"></p>
    </div>  
        
</template>

<script>   

import { ref } from 'vue'
import Racer from "@/components/Racer.vue"
import Carousel from '@/components/Carousel.vue'
import CarouselSlide from '@/components/CarouselSlide.vue'

export default {
    name: 'Background', 
    components: {
        Racer,Carousel, CarouselSlide
    },
    setup(){

        const pic = ref(require('@/images/Sky3.png'))

        return  { pic }
    },

    data(){
        return{   
            slides: [
                {
                    image_path:  require('@/images/racer.png' ),
                    text: "Для примера мы показали вам его лицо. В первой серии он прячется в подвале"+"\t\n" +
                            "за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу —" + "\t\n" +
                            "ему не терпится отдать вам промокод."
                },

                {
                    image_path: require('@/images/Ron.png' ),
                    text: "Рон - хороший парень" 
                },

                {
                    image_path: require('@/images/Emma.png'),
                    text: "Гермиона"+"\t\n" +
                            "она знает многое, но где находится промокод —" + "\t\n" +
                            "ей неизвестно."
                },
                {
                    image_path: require('@/images/Draco.png'),
                    text: "Драко"+"\t\n" +
                            "недоволен тем, что на него переключили слайд —" + "\t\n" +
                            "листайте дальше."
                },
                {
                    image_path: require('@/images/Severus.png'),
                    text: "Северус только внешне кажется строгим и угрюмым, но тем не менее —"+"\t\n" +
                            "ему ничего не известно про промокод."
                },
                {
                    image_path: require('@/images/Lord.png'),
                    text: "Темному лорду так же не терпится найти промокод "+"\t\n" +
                            "быстрее листайте дальше, пока он не применил запрещенное заклинание —" + "\t\n" +
                            "АВАДА КЕДАВРА."  
                },
                {
                    image_path: require('@/images/Dumbledore.png'),
                    text: "Снова какие-то заумные советы, которые никак не приводят к поиску промокода,"+"\t\n" +
                            "но попросите у него помощи от смертельного заклинания —" + "\t\n" +
                            "чтобы продолжить поиски промокода." 
                },
                {
                    image_path: require('@/images/Spider.png'),
                    text: "Человек-паук пришел к нам из другой вселенной, чтобы показать"+"\t\n" +
                            "где находится промокод, но, увы —" + "\t\n" +
                            "вас убил Темный лорд." 
                }
                
                
                 
                 
            ],


            visibleSlide: 0,
        }
        
    }, 
    computed: {
        slidesLen(){
            return this.slides.length;
        },
        slidesText(){
            return this.slides[this.visibleSlide].text;
        }
        

    },
    methods: {
        getImgUrl(pic) {
            return require('@/images/'+pic)
        },
        next(){
            if(this.visibleSlide >= this.slides.length-1){
                this.visibleSlide = 0;
            }

            else{
                this.visibleSlide++;
            }
             
        },
        prev(){
            if(this.visibleSlide <= 0){
                this.visibleSlide = this.slidesLen - 1;
            }

            else{
                this.visibleSlide--;
            }
        }
    }  

};
 
</script>

<style>   
    .rectLG {
    position: absolute;
    width: 100%;
    height: 27%; 
    z-index: 3;
    background: linear-gradient(0deg, rgba(255, 255, 255, 0.0001) 23.86%, #FFFFFF 82.86%);
     
    }

    .sliderCount{
    position: absolute;
    display: flex;
    width: 4%;
    height: 8%;
    top: 25%;
    left: 48%; 
    background-image: url("@/images/RoundShape.svg");
    background-repeat: no-repeat;
    background-size: contain;
    border: 1px solid rgba(255, 0, 0, 0);
    z-index: 4;
    }

    .sliderCount p{   
    position: absolute; 
    align-self: center;
    font-size: 1vw; 
    left: 30%; 
    font-family: "kinopoisk-semibold";
    }
 

    .background  {     
    min-height: 500px;   
    border: 3px solid rgba(195, 0, 255, 0);
    } 

    .bgImage {
    position: relative;
    width: 100%;   
    }
 
    .slider{ 
    position: absolute;    
    width: 21%;
    height: 55%; 
    }

    .carousel-wrapper {
    padding: 40px;
    }
    
    .clouds {
    position: absolute; 
    width: 100%;   
    z-index: 2; 
    border:2px solid #333333; 
    }
    .sliderImage {   
    width: 100%;      
    }

    .sliderTextContainer {  
    position: absolute;
    width: 70%;
    height: 15%;
    bottom: 20%; 
    z-index: 5;
    color: rgb(0, 0, 0);  
    }

    .sliderTextContainer p{  
    position: absolute;  
    align-self: center;
    width: 100%;
    height: 100%;
    margin-top: -0.1%;
    font-size: 25px;
    line-height: 150%;
    font-size: 1.4vw;
    color: rgb(0, 0, 0); 
    font-family: "kinopoisk-light"; 
    white-space: pre-wrap;
    }

    .buttonArrow {
    position: absolute;  
    width: 17%;
    height: 50%;
    top: 25%; 
    left: 15%;
    right: 0; 
    }
      
 
</style>
