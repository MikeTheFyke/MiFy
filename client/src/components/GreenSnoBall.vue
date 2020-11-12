<template>
    <div id=" GreenSnoBall-Container">
        <div id="SnoBall"></div>
    </div>
</template>

<script>
// import gsap from "gsap"
export default {
  name: 'GreenSnoBall',
    data(){
        return{

        }
    },
        methods : {

        },
        mounted (){

        }
    
}
</script>

<style>

#GreenShoBall-Contianer{
    position: absolute;
    top: 100px;
    background-color: #20203a;
    width: 100%;
    height: 40%;
    text-align: center;
    z-Index: 5;
}

#SnoBall{
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: red;
    margin-top: 200px;
    margin-left: 65%;
}

/* #c4bead; */

</style>