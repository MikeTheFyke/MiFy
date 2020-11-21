<template>
    <div id="space-container">
        <div id="space-container2">
            <div id="Alpha"></div>
            <div id="mercury"></div>
            <div id="venus"></div>
            <div id="terra-container">
                <div id="terra-beta"></div>
                <div id="terra"></div>
            </div>
            <div id="mars-container">
                    <div id="mars-phobos" class="mars-beta"></div>
                    <div id="mars-deimos" class="mars-beta"></div>
                    <div id="mars-element"></div>
            </div>
            <div id="saturn-container">
                <div id="saturn-ring-outer"></div>
                <div id="saturn-ring-inner"></div>
                <div id="saturn"></div>
            </div>
            <div id="jupiter"></div>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";
import motionPath from "gsap/MotionPathPlugin";

gsap.registerPlugin(motionPath)
export default {
        name: 'Spacevue',
        data (){
            return{

            }
        },
        methods: {

        },
        mounted (){
            gsap.to('#Alpha', 5, {rotation: 360, repeat: -1, ease: "Linear.easeInOut" })

            gsap.to("#mercury", {
                    motionPath: {
                        path:[ { x: 85,  y: 85},
                               { x: 170, y:0 },
                               { x: 85,  y: -85 },
                               { x: 0,   y:0 },
                             ],
                    curviness: 1 }, 
                duration: 4, rotation: 360, repeat: -1, ease: "Linear.easeInOut"  })

                gsap.to("#venus", {
                    motionPath: {
                        path:[ { x: 145, y: 145},
                               { x: 290, y: 0 },
                               { x: 145, y:-145 },
                               { x: 0,   y:0 },
                             ],
                curviness: 1 }, 
                duration: 3, rotation: 360, repeat: -1, ease: "Linear.easeInOut" })

                gsap.to("#terra-container", {
                    motionPath: {
                        path:[ { x: 200, y: 200},
                               { x: 400, y: 0 },
                               { x: 200, y:-200 },
                               { x: 0,   y:0 },
                             ],
                    curviness: 1 }, 
                duration: 4, rotation: 360, repeat: -1, ease: "Linear.easeInOut" })

                // gsap.to("#terra-beta", {
                //     motionPath: {
                //         path:[  { x: 20},
                //                 { x: 40},
                //                 { x: 20},
                //                 { x: 0 },
                //              ],
                //     curviness: 1 }, 
                // duration: 2, repeat: -1, ease: "Linear.easeInOut" })

                gsap.to("#mars-container", {
                    motionPath: {
                        path:[ { x: 300, y: 300},
                               { x: 600, y:0 },
                               { x: 300, y:-300 },
                               { x: 0, y:0 },
                             ],
                    curviness: 1 }, 
                duration: 4.5, rotation: 360, repeat: -1, ease: "Linear.easeInOut" })

                gsap.to("#mars-deimos", {
                    motionPath: {
                        path:[ { x: 40},
                               { x: 0 },
                             ],
                    curviness: 1
                }, 
                duration: 2, repeat: -1, ease: "Linear.easeInOut" })

                gsap.to("#mars-phobos", {
                    motionPath: {
                        path:[ { x: 40},
                               { x: 0 },
                             ],
                    curviness: 1
                }, 
                duration: 1.5, repeat: -1, ease: "Linear.easeInOut" })

                gsap.to("#saturn-container", {
                    motionPath: {
                        path:[ { x: 400, y: 400},
                               { x: 800, y:0 },
                               { x: 400, y:-400 },
                               { x: 0, y:0 },
                             ],
                curviness: 1
                }, 
                duration: 5.5,
                repeat: -1, ease: "Linear.easeInOut" })

                gsap.to("#jupiter", {
                    motionPath: {
                        path:[ { x: 500, y: 500},
                               { x: 1050, y:0 },
                               { x: 500, y:-500 },
                               { x: 0, y:0 },
                             ],
                curviness: 1
                }, 
                duration: 5.5,
                repeat: -1, ease: "Linear.easeInOut" })
        }
    
}
</script>

<style scoped>

#space-container{
    position: absolute;
    top: 300px;
    width: 100%;
    height: 400px;
}

#space-container2{
    margin: 0px;
    margin-left: 55vw;
    width: 0px;
    height: 100%;
}

#Alpha{
    height: 100px;
    width: 100px;
    border-radius: 50px;
    background-image: linear-gradient(red, yellow);
}

#mercury{
    position: relative;
    top: -65px;
    left: -50px;
    width: 30px;
    height: 30px;
    border-radius: 15px;
    background-image: linear-gradient(#bfbeac, #65696b);
}

#venus{
    position: relative;
    top: -95px;
    left: -100px;
    width: 40px;
    height: 40px;
    border-radius: 20px;
    background-image: linear-gradient(#c7bf2e, yellow);
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
    background-image: linear-gradient(#bfbeac, #65696b);
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
    background-image: linear-gradient(#f20000, #612722);
}

#mars-phobos{
    position: relative;
    top: 20px;
    width: 5px;
    height: 5px;
    border-radius: 3px;
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

#saturn-container{
    position: absolute;
    top: 0px;
    left: 26%;
}

#saturn{
    position: absolute;
    top: 10px;
    left: 10px;
    width: 70px;
    height: 70px;
    border-radius: 35px;
    background-image: linear-gradient(#d16619, #65696b);
}

#saturn-ring-outer{
    position: absolute;
    top: 0px;
    width: 90px;
    height: 90px;
    border-radius: 45px;
    background-image: linear-gradient(#bfbeac, #65696b);
}

#saturn-ring-inner{
    position: absolute;
    top: 5px;
    left: 5px;
    width: 80px;
    height: 80px;
    border-radius: 40px;
    background-color: #ffffff;
}

#jupiter{
    position: absolute;
    top: 0px;
    left: 17%;
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-image: linear-gradient(#c99793,#c99793, #e34d2b,#c99793, #65696b, #c99793, #65696b, #e34d2b, #65696b);
}
</style>