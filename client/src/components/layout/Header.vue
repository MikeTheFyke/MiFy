<template>
    <div>
        <div id="header-content">
            <button id="header-content-close" v-on:click="headerClose()">X</button>
        </div>    

        <div id="header-bar">
            <button id="header-button" v-on:click="headerExpand()">
                <div class="header-div" id="header-div-top"></div>
                <div class="header-div" id="header-div-middle"></div>
                <div class="header-div" id="header-div-bottom"></div>
            </button>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";

export default {
    name: 'Header',
        data() {
            return {

            }
        },
        methods: {
            headerExpand() {
                gsap.to('#header-content', 1.5, { x: 0 } );
                gsap.to('#header-bar', 1, { backgroundColor: '#0e0e2b' } );
            },
            headerClose() {
                gsap.to('#header-content', 1.5, { x: '-100vw' } );
                gsap.to('#header-bar', 1, { backgroundColor: '#20203a' } );
            }
        }, 
        mounted: function() {
            gsap.to('#header-content', 0, { x: '-100vw' } );

            document.getElementById('header-button').addEventListener('mouseover', function(){
                gsap.to('.header-div', 1.5, { backgroundColor: "white" } );
            });

            document.getElementById('header-button').addEventListener('mouseout', function(){
                gsap.to('.header-div', 1.5, { backgroundColor: "#f20000" } );
            });
        }
    
}
</script>

<style scoped>

#header-content{
    position: absolute;
    top: 0px;
    left: 0px;
    height: 100vw;
    width: 100vw;
    background-color: #20203a;
}

#header-bar{
    position: fixed;
    top: 0px;
    left: 0px;
    width: 10%;
    height: 100vh;
    background-color: #20203a;
    padding: 20px;
    text-align: center;
}

#header-button{
    position: relative;
    top: 0px;
    width: 50px;
    height: 50px;
    background-color: transparent;
    border-color: transparent;
    outline: none;
    padding: 0px;
}

.header-div{
    width: 100%;
    height: 10px;
    border-radius: 5px;
    background-color: #f20000;
    margin-bottom: 5px;
}

#header-div-bottom{
    width: 75%;
}

</style>