<template>
    <div id="Three-Container">

    <h1 id="ThreeTitle">Three Js</h1>

    <div id="scrollContainer2">
      <button id="scrollButton2" @click="scrollDown">Click</button>
    </div>

    </div>
</template>

<script>
export default {
  name: 'Threevue',
  data () {
    return {
      visible: false
    }
  },
  methods: {
    scrollDown: function () {
          window.scroll(0, (window.innerHeight * 3) )
      }
  }
}
</script>

<style scoped>

#scrollContainer2{
  position: absolute;
  bottom: 10px;
  left: 50%;
}

#Three-Container{
    Position: absolute;
    top: 200vh;
    left: 20%;
    width: 80vw;
    height: 100vh;
    background-color: yellow;
}

#ThreeTitle{
    Position: relative;
    top: 20px;
    color: red;
}

</style>