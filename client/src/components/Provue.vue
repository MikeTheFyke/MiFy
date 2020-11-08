<template>
    <div id="Process-Container">
        <h1 id="ProTitle">Processing</h1>

    <div id="scrollContainer">
      <button id="scrollButton" @click="scrollDown">Click</button>
    </div>

    </div>
</template>

<script>
export default {
  name: 'Provue',
  data () {
    return {
      visible: false
    }
  },
  methods: {
    scrollDown: function () {
          window.scroll(0, (window.innerHeight * 2))
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