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
        ctx: null,
        // canvas: null,
        }
    },
        mounted: function () {
            this.ctx = document.getElementById('snowing-canvas').getContext('2d');
            // this.canvas = this.ctx.getContext('2d');

            this.fillCanvas(this.ctx);

            gsap.to("#SnoFlake", { duration: 5, y: '500vw', delay: 5})
        },
        methods: {
                fillCanvas (ctx){
                ctx.fillStyle = "#ff0000";
                ctx.fillRect(0,0,300,150);
        }
    },
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