<template>
  <div id="app">
    <Header />
    <Newvue />
    <Spacevue />
    <!-- <HelloWorld /> -->
    <Provue />
    <Threevue />
    <Greenvue />
  </div>
</template>

<script>
import Header from './components/layout/Header.vue';
import Newvue from './components/Newvue.vue';
import Provue from './components/Provue.vue';
import Threevue from './components/Threevue.vue';
import Greenvue from './components/Green.vue';
import Spacevue from './components/Space.vue';

// import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    Header,
    Newvue,
    Spacevue,
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
