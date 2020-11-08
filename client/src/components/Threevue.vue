<template>
    <div id="Three-Container">


    <div id="scrollContainer">
      <button id="scrollButton" @click="scrollTop">Click</button>
    </div>

    </div>
</template>

<script>
export default {
  name: 'Threevue',
  data () {
    return {
      
    }
  },
  methods: {
    scrollTop: function () {
        this.intervalId = setInterval(() => {
          if (window.pageYOffset === 0) {
            clearInterval(this.intervalId)
          }
          console.log("Window Height = " + window.innerHeight)
          window.scroll(0,window.pageYOffset + (window.innerHeight*3) )
        }, 20)
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

#scrollButton{

}

#Three-Container{
    Position: absolute;
    top: 300vh;
    left: 20%;
    width: 80vw;
    height: 100vh;
    background-color: yellow;
}

</style>