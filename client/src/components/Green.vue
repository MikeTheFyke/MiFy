<template>
    <div id="Green-Container">

    <h1 id="GreenTitle">GSAP</h1>

    </div>
</template>

<script>
export default {
  name: 'Greenvue',
  data () {
    return {
    }
  }
}
</script>

<style scoped>
#Green-Container{
    Position: absolute;
    top: 0px;
    left: 100vw;
    width: 100vw;
    height: 100vh;
    background-color: blue;
}

#GreenTitle{
    Position: relative;
    top: 20px;
    color: red;
}

</style>