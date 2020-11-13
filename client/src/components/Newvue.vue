<template>
    <div>
        <div id="green-container">
            <div id="green-container2">
                <div id="green-element"></div>
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
        // for (var i = 0; i< Infinity; i++){
            // gsap.to("#green-element", 2, { x: '350px', delay: 2, repeat: -1, yoyo: true })
            // gsap.registerPlugin(MotionPathPlugin)
            gsap.to("#green-element", {
                motionPath: {
                    path:[ {x: 200, y:150},
                           {x: 500, y:0},
                         ],
                           curviness:1
                },
                scale: 1.5,
                duration: 2,
                repeat: -1,
                yoyo: true
            })
            // gsap.to("#green-element", 2, { x: 0, delay: 4 })
        // }
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
    width: 40vw;
    height: 100%;
}


#green-element{
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-color: #f20000;;
}

</style>