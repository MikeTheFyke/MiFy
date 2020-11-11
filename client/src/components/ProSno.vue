<template>
    <div id="SnoFlakes-Container">
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
        mouseX: null,
        mouseY: null,
        }
    },
            methods: {
            snowing(ctx){
                var container = { 
                     x: 0,
                     y: 0,
                     width: document.getElementById('snowing-canvas').width,
                     height: document.getElementById('snowing-canvas').height,
                }
                var circles = []
                for (var j = 0; j <= 50; j++){
                    circles.push ({
                                x: Math.floor(Math.random() * (300 - 0 + 1) + 0),
                                y: 10,
                                r: Math.floor(Math.random() * (6 - 1 + 1) + 1),
                                vx: 10,
                                vy: 0,
                                speed: Math.floor(Math.random() * (5 - 2 + 1) + 2),
                    })
                }
                var ball = {
                    ballX: container.width - 40,
                    ballY: container.height - 35,
                    ballR: 10,
                }
                setInterval (function() {
                    ctx.fillStyle = '#a9b1c4';
                    ctx.fillRect(0, 0, 300,150);
                
                    ctx.fillStyle = '#c4bead';
                    ctx.fillRect(0 ,125,300,25);

                    // SnowBall01
                    ctx.fillStyle = '#c4bead';
                    ctx.beginPath();
                    ctx.arc(ball.ballX, ball.ballY, ball.ballR, 0 ,2*Math.PI, true);
                    ctx.fill(); 
                    //

                    for( var i = 0; i < circles.length; i++){
                        ctx.fillStyle = '#c4bead';
                        ctx.beginPath();
                        ctx.arc(circles[i].x, circles[i].y, circles[i].r, 0 ,2*Math.PI, true);
                        ctx.fill(); 

                        if (circles[i].y + circles[i].r + circles[i].vy >= container.height - 15) {
                            circles[i].y = circles[i].vy
                            circles[i].speed = Math.random() * (5 - 1 + 1) + 1
                        }
                        else { 
                            circles[i].y += circles[i].speed
                        }
                    }
                },1000 / this.framesPerSecond)
            }
        },
        mounted () {
            
                this.ctx = document.getElementById('snowing-canvas').getContext('2d');
                this.snowing(this.ctx);

                onmousemove = function(e){
                    console.log("mouse location:", e.clientX, e.clientY)
                    this.mouseX = e.clientX;
                    this.mouseY = e.clientY;
                    }
            
        }
}
</script>

<style scoped>

#SnoFlakes-Container{
    position: absolute;
    top: 100px;
    margin-left: 25%;
    background-color: #20203a;
    width: 50%;
    height: 40%;
    text-align: center;
}

#snowing-canvas{
    width: 100%;
    height: 100%;
}

</style>