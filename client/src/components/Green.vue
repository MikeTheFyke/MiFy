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
      visible: false
    }
  },
  methods: {
    scrollTop: function () {
          window.scroll(0,0)
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
    top: 300vh;
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