<template>
    <Transition name="left">
        <div v-show="visibleSlide === index" class="carousel-slide">
            <slot></slot>
        </div>
    </Transition>
    

    
</template>




<script>
    export default{
        props: ['visibleSlide', 'index'],
        data() {
            return {

            }
        }
    }

</script>




<style>
    .carousel-slide {
    position: absolute;
    width: 100%; 
    z-index: 4;  
    top:0;
    left: 0;
    right: 0;
    bottom: 0;  
    border: 1px solid rgba(0, 0, 255, 0);
    }
    .left-enter-active{
    animation: leftInAnimation 0.5s ease-in-out;

    }
    .left-leave-active{
    animation: leftOutAnimation 0.5s ease-in-out;
    }

    @keyframes leftInAnimation {
    from{transform: translateX(100%);}
    to{transform: translateX(0);}
    }

    @keyframes leftOutAnimation {
    from{transform: translateX(0);}
    to{transform: translateX(-100%);}
    }

</style>