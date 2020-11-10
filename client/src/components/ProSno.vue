<template>
    <div id="SnoFlakes">
        <canvas id="snowing-canvas"></canvas>
    </div>
</template>

<script>
// import gsap from "gsap";

export default {
    data() {
        return {
        ctx: null,
        }
    },
        mounted: function () {
            this.ctx = document.getElementById('snowing-canvas').getContext('2d');
            this.fillCanvas(this.ctx);
            // document.getElementById('snowing-canvas').addEventListener('mouseover', function(){ gsap.to('#snowing-canvas', 0.75, { x: "-300px" } ); });
            // document.getElementById('snowing-canvas').addEventListener('mouseout', function(){ gsap.to('#snowing-canvas', 0.75, { x: 0 } ); });
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
    border-color: #20203a;
    border-style: solid;
    border-width: 5px;
}

</style>