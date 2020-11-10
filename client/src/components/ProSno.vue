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
        canvas: null,
        }, 
        methods: {

        },
        mounted() {
            var ctx = document.getElementById("snowing-canvas");
            canvas = ctx.getContext('2d');

                ctx.fillStyle = "black";
                ctx.fillRect(0,0,this.canvas.width,this.canvas.height);

            gsap.to("#SnoFlake", { duration: 5, y: '500vw', delay: 5})
        }
}
</script>

<style scoped>

#snowing-canvas{
    width: 150px;
    height: 100px;
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