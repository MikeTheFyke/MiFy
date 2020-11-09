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
    }
  },
  methods: {
    init: function() {
        let container = document.getElementById('cube-container');

        this.camera = new Three.PerspectiveCamera(70, container.clientWidth/container.clientHeight, 0.01, 1000);
        
        this.camera.position.z = 5;

        this.scene = new Three.Scene();

        this.raycaster = new Three.Raycaster();
        this.mouse = new Three.Vector2();

//////// Cubes
for (var a = 0; a <= 1; a++){
        let geometry = new Three.BoxGeometry(0.2, 0.2, 0.2,);
        let material = new Three.MeshNormalMaterial(
            //  { wireframe: true } 
        );
        for (var  i = 0; i < 7; i++){
            for (var j = 0; j < 4; j++){
            var mesh = new Three.Mesh(geometry, material);
            mesh.position.x = (-1.25) + (j * 1); 
            mesh.position.y = (-1 + (i * .215));
            mesh.position.z = (3 - (a));
            this.scene.add(mesh);
            }
        }
//////// Larger Cubes
        let geometry2 = new Three.BoxGeometry(0.4, 0.4, 0.4);
        for (var  k = 0; k < 4; k++){
            for (var  l = 0; l < 2; l++){
                for (var  m = 0; m < 2; m++){
                    var mesh2 = new Three.Mesh(geometry2, material);
                    mesh2.position.x = (-1.05 + (l * 0.41) + (m * 2.25)); 
                    mesh2.position.y = (-1 + (k * 0.41));
                    mesh2.position.z = (2.5 - (a));
                    this.scene.add(mesh2);
                }
            }
        }
//////// Top Cubes
        let geometry3 = new Three.BoxGeometry(0.3, 0.3, 0.3);
        for (var n = 0; n < 4; n++){
            var mesh3 = new Three.Mesh(geometry3, material);
            mesh3.position.x = (-1.25 + (n * 1)); 
            mesh3.position.y = (0.55);
            mesh3.position.z = (3 - (a));
            this.scene.add(mesh3);
        }
//////// Mini Top Cubes
        let geometry4 = new Three.BoxGeometry(0.1, 0.1, 0.1);
        for (var o = 0; o < 4; o++){
            for (var p = 0; p < 3; p++){
            var mesh4 = new Three.Mesh(geometry4, material);
            mesh4.position.x = (-1.12 + (o * .2) + (p * 1.1)); 
            mesh4.position.y = (0.49);
            mesh4.position.z = (2.65 - (a));
            this.scene.add(mesh4);
            }
        }
////////
}
        this.light = new Three.PointLight (0xFFFFFF, 1, 500); // Color (white), Intensity, Distance
        this.light.position.set(0,30,0); //light.position.set(10,0,25)
        this.scene.add(this.light);

        this.light = new Three.PointLight (0xFFFFFF, 2, 1000); // Color (white), Intensity, Distance
        this.light.position.set(0,10,25);
        this.scene.add(this.light);

        this.renderer = new Three.WebGLRenderer({antialias: true});
        this.renderer.setSize(container.clientWidth, container.clientHeight);
        this.renderer.setClearColor (0xFFFFFF, 1);
        container.appendChild(this.renderer.domElement);

    },
    animate: function() {
        requestAnimationFrame(this.animate);
        this.renderer.render(this.scene, this.camera);
    }
  },
  mounted() {
      this.init();
      this.animate();
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