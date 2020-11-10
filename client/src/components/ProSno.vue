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
        framesPerSecond : 30,
        }
    },
        mounted: function () {
            setInterval (function() {
            this.ctx = document.getElementById('snowing-canvas').getContext('2d');
                this.ctx.fillStyle = '#a9b1c4';
                this.ctx.fillRect(0,0,300,150);
                
                this.ctx.fillStyle = '#c4bead';
                this.ctx.fillRect(0,125,300,25);
            },1000 / this.framesPerSecond)
        },
        methods: {

        }
}
</script>

<style scoped>

#SnoFlakes{
    position: absolute;
    top: 100px;
    margin-left: 25%;
    background-color: #20203a;
    width: 300px;
    height: 200px;
    text-align: center;
}

#snowing-canvas{
    width: 150px;
    height: 100px;
    margin-top: 50px;
}

</style>