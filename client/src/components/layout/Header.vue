<template>
    <div>
        <div id="header-bar">
            <button id="header-button">
                <div class="header-div" id="header-div-top"></div>
                <div class="header-div" id="header-div-middle"></div>
                <div class="header-div" id="header-div-bottom"></div>
            </button>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>

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
    background-color: #f20000;;
    margin-bottom: 5px;
}

#header-div-bottom{
    width: 75%;
}

</style>