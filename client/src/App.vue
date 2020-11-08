<template>
  <div id="app">
    <Header />
    <div id="scrollContainer">
      <button id="scrollButton" @click="scrollTop">Click</button>
    </div>
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
import Greenvue from './components/Greenvue.vue';

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

<style>

#scrollContainer{
  position: absolute;
  bottom: 10px;
  left: 50%;
}

#scrollButton{

}

</style>
