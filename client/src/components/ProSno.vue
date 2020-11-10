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
            this.ctx = document.getElementById('snowing-canvas').getContext('2d');
            this.fillCanvas(this.ctx);
            this.snowing(this.ctx);
            // document.getElementById('snowing-canvas').addEventListener('mouseover', function(){ gsap.to('#snowing-canvas', 0.75, { x: "-300px" } ); });
            // document.getElementById('snowing-canvas').addEventListener('mouseout', function(){ gsap.to('#snowing-canvas', 0.75, { x: 0 } ); });
        },
        methods: {
                fillCanvas (ctx){
                
                ctx.fillStyle = '#a9b1c4';
                ctx.fillRect(0,0,300,150);
                
                ctx.fillStyle = '#c4bead';
                ctx.fillRect(0,125,300,25);
        },
            snowing : function (ctx) {
                this.intervalid = setInterval(function(){
                var snowY = 0;
                    for( var i = 0; i <= 100; i++){
                        ctx.fillStyle = '#c4bead';
                        ctx.beginPath();
                        ctx.arc(25, snowY + i, 10, 0 ,2*Math.PI);
                        ctx.fill();
                        
                        ctx.fillStyle = '#a9b1c4';
                        ctx.beginPath();
                        ctx.arc(25, snowY + i, 10, 0 ,2*Math.PI);
                        ctx.fill();
                    }
                }, 1000 / this.framesPerSecond)
            }
    },
}
</script>

<style scoped>

#SnoFlakes{
    position: absolute;
    top: 100px;
    left: 300px;
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