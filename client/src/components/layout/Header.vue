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
                <h1 class="contact-text">Mike Fyke</h1>
                <h1 class="contact-text">Toronto, Ontario</h1>
                <h1 class="contact-text">mikefyke@hotmail.com</h1>
                <h1 class="contact-text">1-705-808-1229</h1>
            </div>

    </div>
</template>

<script>
import gsap from "gsap";
import headerIcon from "./../../assets/mify-icon.png";
import contactIcon from "./../../assets/contact-icon.png";

export default {
    name: 'Header',
        data() {
            return {
                headerIcon: headerIcon,
                contactIcon: contactIcon,
                expanded: false,
            }
        },
        methods: {
            headerExpand() {
                gsap.to('#header-content', 1.5, { scaleX: 1, transformOrigin: "left" } );
                gsap.to('#header-bar', 1, { backgroundColor: '#0e0e2b' } );
                gsap.to('#header-button', 0.5, { zIndex: 0, opacity: 0 } );
                gsap.to('#header-icon-container', 0.5, { zIndex: 3, opacity: 1 } );
            },
            headerClose() {
                gsap.to('#header-content', 1.5, { scaleX: 0, transformOrigin: "left" } );
                gsap.to('#header-bar', 1, { backgroundColor: '#20203a' } );
                gsap.to('#header-button', 0.5, { zIndex: 2, opacity: 1 } );
                gsap.to('#header-icon-container', 0.5, { zIndex: 0, opacity: 0 } );
            },
            contactExpand(){
                if (this.expanded === false){
                    gsap.to('#header-contact-container', 1, { y:'-100px'} );
                    this.expanded = true;
                } else if (this.expanded === true){
                    gsap.to('#header-contact-container', 1, { y:0} );
                    this.expanded = false;
                }
            },
        }, 
        mounted: function() {
            gsap.to('#header-content', 0, { scaleX: 0 } );

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
    height: 100vh;
    width: 100vw;
    background-color: #20203a;
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
    position: fixed;
    top: 0px;
    left: 0px;
    height: 100vh;
    width: 10%;
    padding: 20px;
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
    position: absolute;
    bottom: 20px;
    left: 15px;
    width: 10%;
    text-align: center;   
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

.contact-text{
    color: white;
    font-size: 0.8em;
    margin: 0px;
    white-space: nowrap;
}
</style>