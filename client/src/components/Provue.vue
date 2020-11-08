<template>
    <div id="Process-Container">
        <h1 id="ProTitle">Processing</h1>
    <div id="scrollContainer3">
      <button id="scrollButton3" @click="scrollTop">Click</button>
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
    scrollTop: function () {
        this.intervalId = setInterval(() => {
          if (window.pageYOffset === 0) {
            clearInterval(this.intervalId)
          }
          window.scroll(0, window.pageYOffset + window.innerHeight)
        }, 20)
      },
      scrollListener: function () {
        this.visible = window.scrollY > 150
      }
  },
    mounted: function () {
      window.addEventListener('scroll', this.scrollListener)
    },
    beforeDestroy: function () {
      window.removeEventListener('scroll', this.scrollListener)
    }
}
</script>

<style scoped>

#scrollContainer3{
  position: absolute;
  bottom: 10px;
  left: 50%;
}

#Process-Container{
    Position: absolute;
    top: 200vh;
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