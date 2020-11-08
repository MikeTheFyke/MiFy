<template>
  <div id="app">
    <div id="scrollContainer">
      <button id="scrollButton" @click="scrollTop">Click</button>
    </div>
    <Header />
    <HelloWorld />
    <Provue />
    <Threevue />
    <Greenvue />
  </div>
</template>

<script>
import Header from './components/layout/Header.vue';
import HelloWorld from './components/HelloWorld.vue';
import Provue from './components/Provue.vue';
import Threevue from './components/Threevue.vue';
import Greenvue from './components/Green.vue';

export default {
  name: 'App',
  components: {
    Header,
    HelloWorld,
    Provue,
    Threevue,
    Greenvue
  },
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
          console.log("WindowHeight = " + window.innerHeight)
          console.log("PageOffset = " + window.pageYOffset)
          window.scroll(0, window.pageYOffset + window.innerHeight)
        }, 20)
      },
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

</style>
