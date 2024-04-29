<template>
    <view>
        <canvas canvas-id="webgl" :style="{ width: '100%', height: '400px' }"></canvas>
    </view>
</template>

<script setup>
import { onMounted } from 'vue';
import * as THREE from 'three';
const initThreeJS = () => {
    const canvas = uni.createCanvasContext('webgl', this);
    const renderer = new THREE.WebGLRenderer({
        canvas: canvas
    });
    renderer.setSize(window.innerWidth, window.innerHeight);
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(45, window.innerWidth / window.innerHeight, 0.1, 1000);
    camera.position.set(0, 0, 100);
    camera.lookAt(0, 0, 0);
    const geometry = new THREE.BoxGeometry(10, 10, 10);
    const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
    const cube = new THREE.Mesh(geometry, material);
    scene.add(cube);
    renderer.render(scene, camera);
};


onMounted(() => {
    initThreeJS();
});
</script>

<style>
/* 样式 */
</style>