<template>
    <div ref="canvas"   v-on:mousemove="getClients(clients.x, clients.y, $event)" ></div>
</template>

<script>
import * as THREE from "three";
// import gsap from 'gsap'

export default {
    name: 'MyCanvas',
    props: {
    },
    data() {
        const sizes= {
                width: 800,
                height: 600
            }
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
        const renderer = new THREE.WebGLRenderer();

        const geometry = new THREE.BoxGeometry(1, 1, 1);
        const material = new THREE.MeshBasicMaterial({ color: 0xff0000 })
        const mesh = new THREE.Mesh(geometry, material);
        const clock = new THREE.Clock();
        // gsap.to(mesh.position, { delay:2, duration:1, x:3});
        return {
            scene,
            camera,
            mesh,
            renderer,
            sizes,
            clock,
            clients: {
                x: 0,
                y: 0
            },
        }
    },
    created() {

        this.scene.add(this.mesh);
        this.scene.add(this.camera);
        this.renderer.setSize(window.innerWidth, window.innerHeight);
        this.camera.position.z = 3
    },
    mounted: function() {
        this.$refs.canvas.appendChild(this.renderer.domElement)
        this.rotating();
        
    },
    methods: {
        getClients: (x, y, event) => {
            x = event.clientX;
            y = event.clientY;
        },
        rotating: function() {
            // const elapsedTime = this.clock.getElapsedTime()
            this.camera.position.x = -1 *(this.clients.x / window.innerWidth - 0,5); 
            this.camera.position.y = -1 *(this.clients.y / window.innerHeight - 0,5);
            // this.camera.position.x = Math.cos(elapsedTime)
            this.camera.lookAt(this.mesh.position)
            this.renderer.render(this.scene ,this.camera)
            window.requestAnimationFrame(this.rotating)

        }
    },
}

</script>

<style  scoped>

</style>