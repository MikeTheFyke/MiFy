<template>
    <div id="Green-Container">

    <h1 id="GreenTitle">GSAP</h1>

    <div id="scrollContainer">
      <button id="scrollButton" @click="scrollTop">Click</button>
    </div>

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

#scrollContainer{
  position: absolute;
  bottom: 10px;
  left: 50%;
}

#Green-Container{
    Position: absolute;
    top: 200vh;
    left: 20%;
    width: 80vw;
    height: 100vh;
    background-color: blue;
}

#GreenTitle{
    Position: relative;
    top: 20px;
    color: red;
}

</style>