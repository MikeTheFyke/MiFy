<template>
    <div>

        <div id="header-icon-container">
            <div id="header-icon-container2">
                <img :src="headerIcon" id="header-icon">
            </div>
        </div> 

        <div id="header-content">
            <div id="header-close-button-container">
                <button id="header-content-close" v-on:click="headerClose()">X</button>
            </div>

            <div class="text-backA" id="text01-backA"></div>
            <div class="text-backB" id="text01-backB"></div>
            
            <div class="text-backA" id="text02-backA"></div>
            <div class="text-backB" id="text02-backB"></div>
            
            <div class="text-backA" id="text03-backA"></div>
            <div class="text-backB" id="text03-backB"></div>
            
            <div id="content-text-container">
                <img :src="processingText" id="proText" @click="scrollProcessing">
                <img :src="threeText" id="threeText" @click="scrollThree">
                <img :src="gsapText" id="gsapText" @click="scrollGsap">
            </div>
        </div>    

        <div id="header-bar">
            <button id="header-button" v-on:click="headerExpand()">
                <div class="header-div" id="header-div-top"></div>
                <div class="header-div" id="header-div-middle"></div>
                <div class="header-div" id="header-div-bottom"></div>
            </button>
        </div>

        <div id="header-contact-container">
            <button id="contact-button" v-on:click="contactExpand()" ><img :src="contactIcon" id="contact-icon"></button>
            <div id="contact-text-container">
                <h1 class="contact-text">Mike Fyke</h1>
                <h1 class="contact-text">Toronto, Ontario</h1>
                <h1 class="contact-text">mikefyke@hotmail.com</h1>
                <h1 class="contact-text">1-705-808-1229</h1>
            </div>
        </div>

    </div>
</template>

<script>
import gsap from "gsap";
import headerIcon from "./../../assets/mify-icon.png";
import contactIcon from "./../../assets/contact-icon.png";
import processingText from "./../../assets/Processing.png";
import threeText from "./../../assets/ThreeJs.png";
import gsapText from "./../../assets/Gsap.png";

export default {
    name: 'Header',
        data() {
            return {
                headerIcon: headerIcon,
                contactIcon: contactIcon,
                processingText: processingText,
                threeText: threeText,
                gsapText: gsapText,
                expanded: false,
            }
        },
        methods: {
            headerExpand() {
                gsap.to('#header-content', 1, { scaleX: 1, transformOrigin: "left" } );
                gsap.to('#header-bar', 1, { backgroundColor: '#0e0e2b' } );
                gsap.to('#header-button', 0.5, { zIndex: 0, opacity: 0 } );
                gsap.to('#header-icon-container', 0.5, { zIndex: 5, opacity: 1 } );
            },
            headerClose() {
                gsap.to('#header-content', 1, { scaleX: 0, transformOrigin: "left" } );
                gsap.to('#header-bar', 1, { backgroundColor: '#20203a' } );
                gsap.to('#header-button', 0.5, { zIndex: 2, opacity: 1 } );
                gsap.to('#header-icon-container', 0.5, { zIndex: 0, opacity: 0 } );
            },
            contactExpand(){
                if (this.expanded === false){
                    gsap.to('#header-contact-container', 0.5, { y:'-110px'} );
                    gsap.to('#contact-text-container', 0.5, { opacity: 1 } );
                    this.expanded = true;
                } else if (this.expanded === true){
                    gsap.to('#header-contact-container', 0.5, { y:0} );
                    gsap.to('#contact-text-container', 0.5, { opacity: 0 } );
                    this.expanded = false;
                }
            },
            scrollProcessing() {
                gsap.to('#header-content', 2, { scaleX: 0, transformOrigin: "left" } );
                gsap.to('#header-bar', 1, { backgroundColor: '#20203a' } );
                gsap.to('#header-button', 0.5, { zIndex: 2, opacity: 1 } );
                gsap.to('#header-icon-container', 0.5, { zIndex: 0, opacity: 0 } );
                
                gsap.to("#Process-Container", 2, { y: '-100vh' })
                gsap.to("#Three-Container", 2, { y: 0 })
                gsap.to("#Green-Container", 2, { y: 0 })
                 },
            scrollThree() { window.scroll(0, (window.innerHeight*2)) },
            scrollGsap() { window.scroll(0, (window.innerHeight*3)) },
        }, 
        mounted: function() {
            gsap.to('#header-content', 0, { scaleX: 0 } );

            document.getElementById('header-button').addEventListener('mouseover', function(){
                gsap.to('.header-div', 1.5, { backgroundColor: "white" } );
            });

            document.getElementById('header-button').addEventListener('mouseout', function(){
                gsap.to('.header-div', 1.5, { backgroundColor: "#f20000" } );
            });

            document.getElementById('proText').addEventListener('mouseover', function(){
                gsap.to('#text01-backB', 0.75, { scaleX: 1, transformOrigin: "left" } );
            });

            document.getElementById('proText').addEventListener('mouseout', function(){
                gsap.to('#text01-backB', 0.75, { scaleX: 0, transformOrigin: "left" } );
            });

            document.getElementById('threeText').addEventListener('mouseover', function(){
                gsap.to('#text02-backB', 0.75, { scaleX: 1, transformOrigin: "left" } );
            });

            document.getElementById('threeText').addEventListener('mouseout', function(){
                gsap.to('#text02-backB', 0.75, { scaleX: 0, transformOrigin: "left" } );
            });

            document.getElementById('gsapText').addEventListener('mouseover', function(){
                gsap.to('#text03-backB', 0.75, { scaleX: 1, transformOrigin: "left" } );
            });

            document.getElementById('gsapText').addEventListener('mouseout', function(){
                gsap.to('#text03-backB', 0.75, { scaleX: 0, transformOrigin: "left" } );
            });
        }
    
}
</script>

<style scoped>

#header-content{
    position: absolute;
    top: 0px;
    left: 0px;
    height: 100%;
    width: 100vw;
    background-color: #20203a;
    z-index: 4;
}

#header-close-button-container{
    position: relative;
    top: 0px;
    right: 60px;
    width: 100%;
    height: 50px;
    padding: 30px;
}

#header-content-close{
    position: relative;
    top: 0px;
    float: right;
    font-size: 50px;
    color: #f20000;
    background-color: transparent;
    border-color: transparent;
    outline: none;
    cursor: pointer;
}
/*  */
#text01-backA{
    position: absolute;
    top: 165px;  
    background-color:white;
    width: 575px;
    height: 100px;
    margin-left: 300px;
}

#text01-backB{
    position: absolute;
    top: 165px;  
    background-color:#f20000;
    width: 575px;
    height: 100px;
    margin-left: 300px;
    border-bottom-right-radius: 100px;
    transform: scaleX(0);
}

#text02-backA{
    position: absolute;
    top: 275px;  
    background-color:white;
    width: 530px;
    height: 100px;
    margin-left: 300px;
}

#text02-backB{
    position: absolute;
    top: 275px;  
    background-color:#f20000;
    width: 530px;
    height: 100px;
    margin-left: 300px;
    border-bottom-right-radius: 100px;
    transform: scaleX(0);
}

#text03-backA{
    position: absolute;
    top: 390px;  
    background-color:white;
    width: 530px;
    height: 100px;
    margin-left: 300px;
}

#text03-backB{
    position: absolute;
    top: 390px;  
    background-color:#f20000;
    width: 530px;
    height: 100px;
    margin-left: 300px;
    border-bottom-right-radius: 100px;
    transform: scaleX(0);
}

#content-text-container{
    position: relative;
    top: 50px;
    margin-left: 300px;
    width: 700px;
}

/*  */
#header-bar{
    position: fixed;
    top: 0px;
    left: 0px;
    width: 15%;
    height: 100vh;
    background-color: #20203a;
    padding: 20px;
    text-align: center;
    z-index: 4;
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
    cursor: pointer;
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

#header-icon-container{
    position: absolute;
    top: 0px;
    left: 35px;
    height: 100vh;
    width: 10%;
    padding: 20px;
    z-index: 4;
}

#header-icon-container2{
    width: 100%;
    text-align: center;
}

#header-icon{
    width: 50px;
    height: 50px;
}

#header-contact-container{
    position: fixed;
    bottom: -110px;
    width: 15%;
    text-align: center;
    padding: 10px;
    z-index: 5;   
}

#contact-button{
    background-color: transparent;
    border-color: transparent;
    outline: none;
}

#contact-icon{
    width: 75px;
    height: 75px;
}

#contact-text-container{
    margin-top: 20px;
    opacity: 0;
}

.contact-text{
    color: white;
    font-size: calc(6px + .5vw);
    white-space: nowrap;
}
</style>