<template>
    <div id="Green-Container">

    <h1 id="GreenTitle">GSAP</h1>
    <GreenSno />
    </div>
</template>

<script>
import GreenSno from './GreenSno'
export default {
  name: 'Greenvue',
    components: {
      GreenSno : GreenSno,
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped>
#Green-Container{
    Position: absolute;
    top: 0px;
    left: 100vw;
    width: 100vw;
    height: 100vh;
    background-color: blue;
    opacity: 0;
}

#GreenTitle{
    Position: relative;
    top: 20px;
    left: 20%;
    color: red;
}

</style>