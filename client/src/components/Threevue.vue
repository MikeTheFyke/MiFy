<template>
    <div id="Three-Container">

    <h1 id="ThreeTitle">Three Js</h1>
    <!-- <ThrCube /> -->
    </div>
</template>

<script>
// import ThrCube from 'ThrCube.vue';

export default {
  name: 'Threevue',
  components: {
    // ThrCube
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped>
#Three-Container{
    Position: absolute;
    top: -100vh;
    left: 0px;
    width: 100vw;
    height: 100vh;
    background-color: yellow;
    opacity: 0;
}

#ThreeTitle{
    Position: relative;
    top: 20px;
    left: 20%;
    color: red;
}

</style>