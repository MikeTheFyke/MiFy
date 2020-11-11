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
                // var circle = {
                //     x: Math.floor(Math.random() * (max - min + 1) + min),
                //     y: 10,
                //     r: 10,
                //     vx: 10,
                //     vy: 9,
                // }
                var circles = []
                for (var j = 0; j <= 50; j++){
                    circles.push ({
                                x: Math.floor(Math.random() * (max - min + 1) + min),
                                y: 10,
                                r: Math.floor(Math.random() * (6 - 1 + 1) + 1),
                                vx: 10,
                                vy: 0,
                                speed: Math.floor(Math.random() * (5 - 2 + 1) + 2),
                    })
                    console.log(circles)
                }
                setInterval (function() {
                    ctx.fillStyle = '#a9b1c4';
                    ctx.fillRect(0, 0, 300,150);
                
                    ctx.fillStyle = '#c4bead';
                    ctx.fillRect(0 ,125,300,25);

                    
                    for( var i = 0; i < circles.length; i++){
                        ctx.fillStyle = '#c4bead';
                        ctx.beginPath();
                        ctx.arc(circles[i].x, circles[i].y, circles[i].r, 0 ,2*Math.PI, true);
                        ctx.fill();
                        
                        if (circles[i].y + circles[i].r + circles[i].vy >= container.height - 50){
                            circles[i].y = circles[i].vy
                            circles[i].speed = Math.random() * (5 - 1 + 1) + 1
                        }

                        else{
                            circles[i].y += circles[i].speed
                        }
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