<template>
    <div id="SnoFlakes">
        <div id="SnoFlake">
            <canvas id="snowing-canvas"></canvas>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";

export default {
    data() {
        return{
            ctx: "2D",
            canvas: document.getElementById("snowing-canvas"),
        }
    }, 
        methods: {

        },
        mounted() {
            
            gsap.to("#SnoFlake", { duration: 5, y: '500vw', delay: 5})
        }
}
</script>

<style scoped>

#flake{
    position: absolute;
    top: 50px;
    left: 30vw;
    width: 50px;
    height: 50px;
    border-radius: 25px;
    background-color: white;
}

#SnoFlake{
    position: absolute;
    top: 50px;
    left: 50vw;
    width: 50px;
    height: 50px;
    border-radius: 25px;
    background-color: white;
}

</style>