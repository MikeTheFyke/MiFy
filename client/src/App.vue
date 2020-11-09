<template>
  <div id="app">
    <Header />
    <!-- <HelloWorld /> -->
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

// import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    Header,
    // HelloWorld,
    Provue,
    Threevue,
    Greenvue
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped>

</style>
