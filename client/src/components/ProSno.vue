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
        }
    },
        mounted: function () {
            this.ctx = document.getElementById('snowing-canvas').getContext('2d');

            this.fillCanvas(this.ctx);

            document.getElementById('snowing-canvas').addEventListener('mouseover', function(){ gsap.to('#snowing-canvas', 0.75, { x: "-300px" } ); });

            document.getElementById('snowing-canvas').addEventListener('mouseout', function(){ gsap.to('#snowing-canvas', 0.75, { x: 0 } ); });

            gsap.to("#SnoFlake", { duration: 5, y: '500vw', delay: 5})
        },
        methods: {
                fillCanvas (ctx){
                ctx.fillStyle = '#c4bead';
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
    border-radius: 10px;
    border-width: 0.5px;
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