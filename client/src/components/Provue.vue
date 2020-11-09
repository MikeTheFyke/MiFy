<template>
    <div id="Process-Container">
        <h1 id="ProTitle">Processing</h1>
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
    left: 20%;
    width: 80vw;
    height: 100vh;
    background-color: #c4bead;
}

#ProTitle{
    Position: relative;
    top: 20px;
    color: red;
}

</style>