<template>
    <div>
        <div id="green-container">
            <div id="green-container2">
                <div id="green-element"></div>
                <div id="green-element3"></div>
                <div id="green-element2"></div>
                <div id="terra-container">
                    <div id="terra"></div>
                    <div id="terra-beta"></div>
                </div>
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
                gsap.to("#green-element", {
                    motionPath: {
                        path:[ { x: 200, y:150 },
                               { x: 500, y:0 }
                            ],
                            curviness:1
                    },
                    scale: 1.5,
                    duration: 2,
                    repeat: -1,
                    yoyo: true
                })
                gsap.to("#green-element2", {
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


                gsap.to("#green-element3", 1, { scaleX: 0, repeat: -1, yoyo: true, delay: 0.25})
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
    width: 40vw;
    height: 100%;
}


#green-element{
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-color: #f20000;
}

#green-element2{
    position: absolute;
    top: 0px;
    left: 30%;
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-color: #20203a;
}

#green-element3{
    position: absolute;
    top: 0px;
    left: 45%;
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-color: #7a84bf;
}

#terra-container{
    position: absolute;
    top: 0px;
    left: 45%;
    width: 100px;
    height: 100px;
    border-radius: 50px;
    background-color: transparent;
}

#terra{

}

#terra-beta{

}

</style>