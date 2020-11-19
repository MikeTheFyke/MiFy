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
        }
    
}
</script>

<style scoped>

#space-container{
    position: absolute;
    top: 500px;
    width: 100%;
    height: 400px;
}

#space-container2{
    margin: 0px auto;
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

</style>