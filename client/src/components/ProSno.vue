<template>
    <div>
        <div id="SnoFlakes-Container">
            <canvas id="snowing-canvas"></canvas>
            <div id="GreenSnoBall-Container">
                    <div id="SnoBall"></div>
            </div>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";
export default {
    name: 'ProSno',
    data() {
        return {
        ctx: null,
        framesPerSecond : 30,
        mouseX: null,
        mouseY: null,
        canvas: null,
        rect: null,
        }
    },
            methods: {
            
            // BallMove(){
            //     document.getElementById("snowing-canvas").addEventListener("click", function(e){
            //         this.mouseX = e.clientX;
            //         this.mouseY = e.clientY;
            //         console.log("mouse location:", this.mouseX, this.mouseY)
            //         console.log("Clicked")
            //         console.log(this.mouseY - 100)
            //         this.ballCenterX = ((document.getElementById('SnoFlakes-Container').clientWidth / 4) + (document.getElementById('SnoFlakes-Container').clientWidth/2) - 40) + (document.getElementById('SnoFlakes-Container').clientWidth * 0.67);
            //         this.ballCenterY = this.mouseY - 105;
            //         console.log("BallCenterX = " + this.ballCenterX)
            //         console.log("BallCenterY = " + this.ballCenterY)

            //     });
            // },

            snowing(ctx, rect, root){
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
                // var ball = {
                //     ballCenterX: container.width - 40,
                //     ballCenterY: container.height - 35,
                //     ballR: 10,
                // }

                setInterval (function() {

                    document.getElementById("snowing-canvas").addEventListener("click", function(e){

                        gsap.to('#SnoBall', 0, { x: e.clientX - rect.left - root.scrollLeft, y: (e.clientY - rect.top - root.scrollTop) })

                    // ball.ballCenterX = e.clientX - (window.innerWidth / 4 ) ;
                    // this.mouseY = e.clientY;
                    // console.log("Client Width = " + document.getElementById('SnoFlakes-Container').clientWidth)
                    // console.log("Canvas Width = " + document.getElementById('snowing-canvas').width)
                    // console.log("mouse location:", this.mouseX, this.mouseY)
                    // console.log("Clicked")
                    // console.log(this.mouseY - 100)
                    // ball.ballCenterX = this.mouseX - (document.getElementById('SnoFlakes-Container').clientWidth / 4 ) - 80;
                    // ball.ballCenterY = this.mouseY - 105;
                    // console.log("BallCenterX = " + ball.ballCenterX)
                    // console.log("BallCenterY = " + ball.ballCenterY)
                    // console.log(ball.ballCenterX)
                    });
                    ctx.fillStyle = '#a9b1c4';
                    ctx.fillRect(0, 0, 300,150);
                
                    ctx.fillStyle = '#c4bead';
                    ctx.fillRect(0 ,125,300,25);

                    // SnowBall01
                    // ctx.fillStyle = '#c4bead';
                    // ctx.beginPath();
                    // ctx.arc(ball.ballCenterX, ball.ballCenterY, ball.ballR, 0 ,2*Math.PI, true);
                    // ctx.fill(); 
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
            
                this.canvas = document.getElementById('snowing-canvas'); 
                this.ctx = this.canvas.getContext('2d');
                this.rect = this.canvas.getBoundingClientRect();
                this.root = document.documentElement;
                this.snowing(this.ctx, this.rect, this.root);

                // document.getElementById("snowing-canvas").addEventListener("click", this.BallMove(this.e, this.ctx))
        }
}
</script>

<style scoped>

#SnoFlakes-Container{
    position: absolute;
    top: 100px;
    left: 0px;
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

#SnoBall{
    position: absolute;
    top: 100px;
    left: 0px;
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: red;
    margin: 0px;
}
</style>