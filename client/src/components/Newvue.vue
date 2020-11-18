<template>
    <div>
        <div id="green-container">
            <div id="green-container2">
                <div id="mars-container">
                    <div id="mars-phobos" class="mars-beta"></div>
                    <div id="mars-deimos" class="mars-beta"></div>
                    <div id="mars-element"></div>
                </div>
                <div id="alpha-element"></div>
                <div id="mercury-element"></div>
                <div id="venus-element"></div>
                <div id="terra-container">
                    <div id="terra-beta"></div>
                    <div id="terra"></div>
                </div>
                <div id="saturn"></div>
                <div id="jupiter"></div>
                <div id="uranus"></div>
                <div id="neptune"></div>
                <div id="pluto"></div>
            </div>
        </div>
    </div>    
</template>

<script>
import gsap from "gsap";
import motionPath from "gsap/MotionPathPlugin";

gsap.registerPlugin(motionPath)

export default {
    name: 'Newvue',
    data (){
        return{

        }
    },
    methods : {

    },
    mounted (){
            function go(){
                // gsap.to("#mars-element", {
                //     motionPath: {
                //         path:[ { x: 200, y:150 },
                //                { x: 500, y:0 }
                //             ],
                //             curviness:1
                //     },
                //     // scale: 1.5,
                //     duration: 2,
                //     repeat: -1,
                //     yoyo: true
                // })

                gsap.to("#mars-container", {
                    motionPath: {
                        path:[ { x: 275, y: 50},
                               { x: 550, y:0 },
                               { x: 275, y:-25 },
                               { x: 0, y:0 },
                             ],
                curviness: 1
                }, 
                duration: 5,
                repeat: -1, 
                })

                gsap.to(".mars-beta", {
                    motionPath: {
                        path:[ { x: 40},
                               { x: 0 },
                             ],
                curviness: 1
                }, 
                duration: 2,
                repeat: -1, 
                })

                gsap.to("#mercury-element", {
                    motionPath: {
                        path:[ { x: 75, y: 50},
                               { x: 150, y:0 },
                               { x: 75, y:-25 },
                               { x: 0, y:0 },
                             ],
                curviness: 1
                }, 
                duration: 5,
                repeat: -1, 
                })

                gsap.to("#venus-element", {
                    motionPath: {
                        path:[ { x: 125, y: 50},
                               { x: 250, y:0 },
                               { x: 125, y:-25 },
                               { x: 0, y:0 },
                             ],
                curviness: 1
                }, 
                duration: 5,
                repeat: -1, 
                })

                gsap.to("#terra-container", {
                    motionPath: {
                        path:[ { x: 200, y: 50},
                               { x: 400, y:0 },
                               { x: 200, y:-25 },
                               { x: 0, y:0 },
                             ],
                curviness: 1
                }, 
                duration: 5,
                repeat: -1, 
                })

                gsap.to("#terra-beta", {
                    motionPath: {
                        path:[ { x: 40},
                               { x: 0 },
                             ],
                curviness: 1
                }, 
                duration: 2,
                repeat: -1, 
                })

                gsap.to("#alpha-element", 1, { scaleX: 0, repeat: -1, yoyo: true, delay: 0.25})
            }
            go()
    }
}
</script>

<style scoped>

#green-container{
    position: absolute;
    top: 200px;
    width: 100%;
    height: 200px;
}

#green-container2{
    margin: 0px auto;
    width: 20vw;
    height: 100%;
}

#mars-container{
    position: absolute;
    top: 0px;
    left: 32%;
}

#mars-element{
    width: 40px;
    height: 40px;
    border-radius: 20px;
    background-color: #f20000;
}

#mars-phobos{
    position: relative;
    top: 20px;
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: #6b6b63;
}

#mars-deimos{
    position: relative;
    top: 30px;
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: #ababa4;
}

#mercury-element{
    position: absolute;
    top: 0px;
    left: 47%;
    width: 30px;
    height: 30px;
    border-radius: 15px;
    background-color: #bfbeac;
}

#venus-element{
    position: absolute;
    top: 0px;
    left: 43%;
    width: 40px;
    height: 40px;
    border-radius: 20px;
    background-color: #c7bf2e;
}

#alpha-element{
    position: absolute;
    top: 0px;
    left: 50%;
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-image: linear-gradient(red, yellow);
}

#terra-container{
    position: absolute;
    top: 0px;
    left: 37%;
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-color: transparent;
}

#terra{
    width: 50px;
    height: 50px;
    border-radius: 25px;
    background-color: #4f64e0;
}

#terra-beta{
    position: relative;
    top: 0px;
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: #bcc0d6;
}

#saturn{
    width: 70px;
    height: 70px;
    border-radius: 35px;
    background-color: #d16619;
}

#jupiter{
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-color: #e34d2b;
}

</style>