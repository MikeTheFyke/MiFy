<template>
    <div id="Three-Container">

    <div id="scrollContainer4">
      <button id="scrollButton4" @click="scrollTop">Click</button>
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
    scrollTop: function () {
        this.intervalId = setInterval(() => {
          if (window.pageYOffset === 0) {
            clearInterval(this.intervalId)
          }
          window.scroll(0, window.pageYOffset + window.innerHeight*4)
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

#scrollContainer4{
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
    background-color: #c4b486;
}

</style>