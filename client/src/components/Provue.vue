<template>
    <div id="Process-Container">
        <h1 id="ProTitle">Processing</h1>

        <div>

        </div>  
    </div>
</template>

<script>
export default {
  name: 'Provue',
  data () {
    return {
    }
  }
}
</script>

<style scoped>

#Process-Container{
    Position: absolute;
    top: 100vh;
    left: 0px;
    width: 100vw;
    height: 100vh;
    background-color: #c4bead;
    opacity: 0;    
}

#ProTitle{
    Position: relative;
    top: 20px;
    left: 20%;
    color: red;
}

</style>