<template>
    <div id="space-container">
        <div id="space-container2">
            <div id="Alpha"></div>
        </div>
    </div>
</template>

<script>

export default {
        name: 'Spacevue',
        data (){
            return{

            }
        },
        methods: {

        },
        mounted (){

        }
    
}
</script>

<style scoped>

#space-container{
    position: absolute;
    top: 600px;
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

</style>