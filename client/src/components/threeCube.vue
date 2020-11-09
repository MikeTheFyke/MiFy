<template>
    <div>
        <div id="cube-container">
        </div>    
    </div>
</template>

<script>
import * as Three from 'three'

export default {
  name: 'ThreeCube',
  data() {
    return {
      camera: null,
      scene: null,
      renderer: null,
      mesh: null,
      light: null,
      raycaster: null,
      mouse: null,
      meshX: -10,
      max: 0.9,
      min: 0.5,
    }
  },
  methods: {
    init: function() {
        let container = document.getElementById('cube-container');

        this.camera = new Three.PerspectiveCamera(70, container.clientWidth/container.clientHeight, 0.01, 10);
        this.camera.position.z = 2;

        this.scene = new Three.Scene();

        let geometry = new Three.BoxGeometry(0.2, 0.2, 0.2,);
        let material = new Three.MeshNormalMaterial();

        this.raycaster = new Three.Raycaster();
        this.mouse = new Three.Vector2();

        for (var  i = 0; i < 25; i++){
            var mesh = new Three.Mesh(geometry, material);
            // mesh.position.x = (Math.random() * (this.max - this.min)) + this.min; 
            // mesh.position.y = (Math.random() * (this.max - this.min)) + this.min; 
            // mesh.position.z = (Math.random() * (this.max - this.min)) + this.min; 
            mesh.position.x = (Math.random() - 0.5) * 2.5; 
            mesh.position.y = (Math.random() - 0.5) * 2.5;
            mesh.position.z = (Math.random() - 0.5) * 2.5;
            this.scene.add(mesh);
            this.meshX+=1;
        }

        this.light = new Three.PointLight (0xFFFFFF, 1, 500); // Color (white), Intensity, Distance
        this.light.position.set(0,30,0); //light.position.set(10,0,25)
        this.scene.add(this.light);

        this.light = new Three.PointLight (0xFFFFFF, 2, 1000); // Color (white), Intensity, Distance
        this.light.position.set(0,10,25);
        this.scene.add(this.light);

        this.renderer = new Three.WebGLRenderer({antialias: true});
        this.renderer.setSize(container.clientWidth, container.clientHeight);
        container.appendChild(this.renderer.domElement);

    },
    onMouseMove : function (event){ // Change color on mouse click to red.
    event.preventDefault();
    this.mouse.x = (event.clientX / window.innerWidth) * 2 - 1; 
    this.mouse.y = (event.clientY / window.innerHeight) * 2 - 1;

    this.raycaster.setFromCamera(this.mouse, this.camera);

    var intersects = this.raycaster.intersectObjects(this.scene.children, true);
    for (var i = 0; i < intersects.length; i ++){
        intersects[i].object.material.color.set(0xff0000);
    }
    },
    animate: function() {
        requestAnimationFrame(this.animate);
        // this.mesh.rotation.x += 0.01;
        // this.mesh.rotation.y += 0.02;
        this.renderer.render(this.scene, this.camera);
    }
  },
  mounted() {
      this.init();
      this.animate();
      window.addEventListener('mousemove', onMouseMove() );
  }
}
</script>

<style scoped>

#cube-container{
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100vw;
    height: 100vh;
}

</style>