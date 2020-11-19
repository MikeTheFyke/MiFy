<template>
    <div id="space-container">
        <div id="space-container2">
            <div id="Alpha"></div>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";
import motionPath from "gsap/MotionPathPlugin";

gsap.registerPlugin(motionPath)
export default {
        name: 'Spacevue',
        data (){
            return{

            }
        },
        methods: {

        },
        mounted (){
            gsap.to('#Alpha', 5, {rotation: 360, repeat: -1, ease: "Linear.easeInOut" })
        }
    
}
</script>

<style scoped>

#space-container{
    position: absolute;
    top: 500px;
    width: 100%;
    height: 400px;
}

#space-container2{
    margin: 0px auto;
    width: 0px;
    height: 100%;
}

#Alpha{
    height: 100px;
    width: 100px;
    border-radius: 50px;
    background-image: linear-gradient(red, yellow);
}

</style>