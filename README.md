# Learning Three.js: Creating a Red Cube

In this lesson, you've learned the basics of creating a 3D scene using Three.js. You've created a red cube, added a camera, and rendered the scene to a WebGL canvas. Here's a breakdown of the key concepts covered in your code:

## 1. Scene

To create a 3D scene in Three.js, you first need to instantiate a new `THREE.Scene` object:

```javascript
const scene = new THREE.Scene();
```

## 2. Red Cube

To create a red cube, you need two components: a geometry and a material. In this case, you're using a `BoxGeometry` for the shape and a `MeshBasicMaterial` with a red color:

```javascript
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({ color: 0xff0000 });
```

Next, create a mesh object by combining the geometry and material:

```javascript
const mesh = new THREE.Mesh(geometry, material);
```

Finally, add the mesh object to the scene:

```javascript
scene.add(mesh);
```

## 3. Camera

To view the 3D scene, you need to add a camera. In this example, you're using a `PerspectiveCamera`, which simulates the way humans perceive depth:

```javascript
const camera = new THREE.PerspectiveCamera(75, sizes.width / sizes.height);
```

Set the camera's position and add it to the scene:

```javascript
camera.position.z = 3;
camera.position.x = 2;
camera.position.y = 1;
scene.add(camera);
```

## 4. Renderer

To display the 3D scene on a webpage, you need to render it using a WebGL renderer. First, select the canvas element from the DOM:

```javascript
const canvas = document.querySelector(".webgl");
```

Then, create a `WebGLRenderer` object and pass in the canvas element:

```javascript
const renderer = new THREE.WebGLRenderer({
  canvas,
});
```

Set the renderer's size to match the desired dimensions:

```javascript
renderer.setSize(sizes.width, sizes.height);
```

Finally, render the scene with the camera:

```javascript
renderer.render(scene, camera);
```

By following these steps, you've successfully created a simple 3D scene using Three.js.
