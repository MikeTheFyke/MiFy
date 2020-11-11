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
        }
    },
            methods: {
            snowing(ctx){
                var max = 300;
                var min = 0;
                var container = { 
                     x: 0,
                     y: 0,
                     width: 300,
                     height: 200,
                }
                var circle ={
                    x: Math.floor(Math.random() * (max - min + 1) + min),
                    y: 10,
                    r: 10,
                    vx: 10,
                    vy: 9,
                }
                setInterval (function() {
                    ctx.fillStyle = '#a9b1c4';
                    ctx.fillRect(0, 0, 300,150);
                
                    ctx.fillStyle = '#c4bead';
                    ctx.fillRect(0 ,125,300,25);

                    
                    for( var i = 0; i < 1; i++){
                        ctx.fillStyle = '#c4bead';
                        ctx.beginPath();
                        ctx.arc(circle.x, circle.y, circle.r, 0 ,2*Math.PI, true);
                        ctx.fill();
                        
                        if (circle.y + circle.r + circle.vy >= container.height - 50 || 
                            circle.y - circle.r + circle.vy < container.y){
                            circle.vy = -circle.vy
                        }

                        
                        circle.y += circle.vy
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