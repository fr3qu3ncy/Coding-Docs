**Three.js: A Comprehensive Guide**
=====================================

**Summary**
------------

This document serves as an in-depth guide to using the popular JavaScript library, Three.js. With its vast array of features and capabilities, Three.js is ideal for creating stunning 3D graphics, animations, and interactive experiences within web browsers. This document covers the basics of getting started with Three.js, advanced use cases, and provides example code snippets to help solidify your understanding.

**Getting Started with Three.js**
-------------------------------

### Installing Three.js

Before diving into the world of Three.js, you'll need to install the library in your project. You can do this by running the following command in your terminal:

```bash
npm install three
```

Alternatively, if you're using a CDN, you can include the script tag in your HTML file:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
```

### Creating Your First Scene

With Three.js installed, let's create our first scene. This involves setting up an HTML file and a JavaScript file to hold the code.

**index.html**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Three.js Tutorial</title>
    <style>
        #canvas {
            width: 400px;
            height: 300px;
            border: 1px solid black;
        }
    </style>
</head>
<body>
    <div id="canvas"></div>
    <script src="script.js"></script>
</body>
</html>
```

**script.js**

```javascript
// Import the Three.js library
import * as THREE from 'three';

// Create a new scene, camera, and renderer
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, 1, 0.1, 1000);
const renderer = new THREE.WebGLRenderer({
    canvas: document.getElementById('canvas'),
});

// Set the dimensions of the renderer
renderer.setSize(400, 300);

// Create a box geometry and mesh
const geometry = new THREE.BoxGeometry();
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const cube = new THREE.Mesh(geometry, material);

// Add the cube to the scene
scene.add(cube);

// Position the camera
camera.position.z = 5;

// Render the scene
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}
animate();
```

This code sets up a basic scene with a green box and renders it within an HTML canvas.

**Advanced Use Cases**
-------------------

### Lighting

Three.js provides various types of lights to enhance your 3D scenes. Here's an example of using a directional light:

```javascript
// Create a new directional light
const light = new THREE.DirectionalLight(0xffffff, 1);
light.position.set(5, 2, 10);

// Add the light to the scene
scene.add(light);
```

### Animations

To create animations in Three.js, you'll need to use the `requestAnimationFrame` function. Here's an example of animating a cube:

```javascript
function animate() {
    requestAnimationFrame(animate);

    // Rotate the cube around its y-axis
    cube.rotation.y += 0.01;

    // Render the scene
    renderer.render(scene, camera);
}
animate();
```

### Physics

For more complex scenes that require physics-based simulations, you can use external libraries such as Ammo.js or P5.js.

**Sources for Learning More**
-----------------------------

*   Three.js Documentation: <https://threejs.org/docs/>
*   Three.js GitHub Repository: <https://github.com/mrdoob/three.js>
*   Web Development Tutorials by FreeCodeCamp: <https://www.freecodecamp.org/learn/web-development-tutorials/>

Sources:

[1] - Three.js Documentation
[2] - Three.js GitHub Repository

Citing Sources:

If you're using this document as a reference, please cite the sources mentioned above.