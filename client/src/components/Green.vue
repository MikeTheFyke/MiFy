<template>
    <div id="Green-Container">

    <!-- <div id="scrollContainer5">
      <button id="scrollButton5" @click="scrollTop">Click</button>
    </div> -->

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

#scrollContainer5{
  position: absolute;
  bottom: 10px;
  left: 50%;
}

#Green-Container{
    Position: absolute;
    top: 400vh;
    left: 20%;
    width: 80vw;
    height: 100vh;
    background-color: blue;
}

</style>