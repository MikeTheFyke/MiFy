<template>
    <div id="Process-Container">
      <div id=TitleContainer>
        <h1 id="ProTitle">Processing</h1>
      </div>
        <div>

        </div>  
        <ProSno />
    </div>
</template>

<script>
import ProSno from './ProSno.vue'

export default {
  name: 'Provue',
  components: {
    ProSno: ProSno,
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped>

#Process-Container{
    Position: absolute;
    top: 100vh;
    left: 0px;
    width: 100vw;
    height: 100vh;
    background-color: white;
    opacity: 0;
}

#TitleContainer{
  width: 100%;
}

#ProTitle{
    Position: relative;
    top: 0px;
    left: 20%;
    color:  #f20000;
    font-size: 80px;
    width: 375px;
    margin: 0px 20vw;
}

</style>