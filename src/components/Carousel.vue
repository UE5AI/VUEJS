<template>
    <div class="carousel">
        <slot></slot> 
        <!-- <button @click="prev" class="prev">Prev</button> -->
    </div>


</template>




<script>
    export default{
        methods: {
            next(){
                this.$emit('next')
            },
            prev(){
                this.$emit('prev')
            }
        }
    }
 
</script>




<style>
    .carousel {  
    position: absolute;
    width: 100%;  
    height: 100%;
    margin-top: 82%; 
    right: 9%;
    z-index: 2;   
    overflow: hidden;  
    border: 2px solid rgba(0, 128, 0, 0);
    }

    .carousel p{
    position: absolute;
    color:rgb(255, 0, 0); 
    bottom: 90%;
    z-index: 50;
    }

    button {
    position: absolute;  
    display: flex;
    height: 6%;
    width: 6%;
    top: 48.8%;
    left: 78.5%;
    background-color: rgba(0, 0, 0, 0);
    border: none;
    z-index: 3;
    color: white; 
    }

    button:focus, button:hover {
    outline: none;
    cursor: pointer; 
    }

    .next {
    position: absolute; 
    right: 0%;    
    width: 2.9%;
    background-image: url("@/images/Circle.svg");
    background-repeat: no-repeat;
    background-size: contain;
    border-radius: 50%;
    }

    .next img{
    position: absolute;   
    width: 30%;
    left: 33%;
    }

    .prev {
    left: 0%;
    }

</style>