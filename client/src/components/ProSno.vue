<template>
    <div id="SnoFlakes">
        <canvas id="snowing-canvas"></canvas>
        <div id="SnoFlake">
        </div>
    </div>
</template>

<script>
import gsap from "gsap";

export default {
    data() {
        return {
        canvas: null,

        }
    },
    methods: {

    },
        mounted() {
            var ctx = document.getElementById("snowing-canvas");
            this.canvas = ctx.getContext('2d');

                this.ctx.fillStyle = "black";
                this.ctx.fillRect(0,0,this.canvas.width,this.canvas.height);

            gsap.to("#SnoFlake", { duration: 5, y: '500vw', delay: 5})
        }
}
</script>

<style scoped>

#snowing-canvas{
    position: absolute;
    top: 100px;
    left: 300px;
    width: 150px;
    height: 100px;
    border-color: black;
    border-style: solid;
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