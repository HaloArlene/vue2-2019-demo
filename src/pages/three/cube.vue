<template>
  <div>
    <breadcrumb :crumbs="['Three', 'Cube']"/>
    <div class="main-page">
      <div class="three-canvas-frame" id="canvas-frame"></div>
    </div>
  </div>
</template>

<script>
  import * as THREE from 'three'
  import ThreeMixin from './mixin/threeMixin'
  import Breadcrumb from "../../components/breadcrumb";

  export default {
    name: "cubeDemo",
    components: {Breadcrumb},
    mixins: [ThreeMixin],
    data() {
      return {
        stats: null,
        cubes: [],
        animationId: null
      }
    },
    beforeDestroy() {
      if (this.cubes.length) {
        this.cubes.forEach(cube => {
          cube.geometry.dispose();
          cube.material.dispose();
        });
      }
      this.stats = null;
    },
    mounted() {
      this.renderer = this.createRenderer();
      this.scene = this.createScene();
      this.camera = this.createCamera(75, 0.1, 5);
      this.camera.position.z = 3;

      const light = new THREE.DirectionalLight(0xFFFFFF, 1);
      light.position.set(-1, 2, 4);
      this.scene.add(light);

      const geometry = new THREE.BoxGeometry(1, 1, 1);
      this.cubes = [
        this.createCube(geometry, 0xFF99E5, 0),
        this.createCube(geometry, 0x44aa88, 2),
        this.createCube(geometry, 0x8844aa, -2)
      ];
      this.cubes.forEach(cube => {
        this.scene.add(cube);
      });

      const Stats = require('stats.js');
      this.stats = new Stats();
      this.stats.showPanel(1);
      this.stats.dom.style.position = 'absolute';
      document.getElementById('canvas-frame').appendChild(this.stats.dom);

      const animation = time => {
        this.stats.begin();
        time *= 0.001;
        this.cubes.forEach((cube, index) => {
          const speed = 1 + index * .1;
          const rot = speed * time;
          cube.rotation.x = rot;
          cube.rotation.y = rot;
        });
        this.renderer.render(this.scene, this.camera);
        this.stats.end();
        this.animationId = requestAnimationFrame(animation);
      };
      animation();
    },
    methods: {
      createCube(geometry, color, x) {
        const material = new THREE.MeshPhongMaterial({color});
        const cube = new THREE.Mesh(geometry, material);
        cube.position.x = x;
        return cube;
      }
    }
  }
</script>
