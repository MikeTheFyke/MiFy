<template>
    <div id="SnoFlakes">
        <canvas id="snowing-canvas"></canvas>
    </div>
</template>

<script>
// import gsap from "gsap";
export default {
    name: 'ProSno',
    data() {
        return {
        ctx: null,
        framesPerSecond : 30,
        x: 0,
        y: 0,
        r: 10,
        vx: 10,
        vy: 9,
        color: 125,
        }
    },
            methods: {
            snowing(ctx){
                setInterval (function() {
                    ctx.fillStyle = '#a9b1c4';
                    ctx.fillRect(0,0,300,150);
                
                    ctx.fillStyle = '#c4bead';
                    ctx.fillRect(0,125,300,25);

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

                },1000 / this.framesPerSecond)
            }
        },
        mounted () {
            
                this.ctx = document.getElementById('snowing-canvas').getContext('2d');
                this.snowing(this.ctx);
            
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