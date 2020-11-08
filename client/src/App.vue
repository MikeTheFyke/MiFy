<template>
  <div id="app">
    <div id="scrollContainer">
      <button id="scrollButton" @click="scrollDown">Click</button>
    </div>
    <Header />
    <Provue />
    <Threevue />
    <Greenvue />
  </div>
</template>

<script>
import Header from './components/layout/Header.vue';
import Provue from './components/Provue.vue';
import Threevue from './components/Threevue.vue';
import Greenvue from './components/Green.vue';

export default {
  name: 'App',
  components: {
    Header,
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
    scrollDown: function () {
          window.scroll(0, window.pageYOffset + window.innerHeight)
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

</style>
