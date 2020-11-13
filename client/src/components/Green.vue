<template>
    <div id="Green-Container">
      <div>
        <h1 id="GreenTitle">GSAP</h1>
      </div>
    <ProSno />
    <!-- <GreenSnoBall /> -->
    </div>
</template>

<script>
// import GreenSnoBall from './GreenSnoBall'
import ProSno from './ProSno'
export default {
  name: 'Greenvue',
    components: {
      // GreenSnoBall : GreenSnoBall,
      ProSno : ProSno,
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
    background-color: white;
    opacity: 0;
}

#GreenTitle{
    Position: relative;
    top: 20px;
    left: 20%;
    color: red;
}

</style>