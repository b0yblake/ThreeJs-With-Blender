## Cameras with mouse

### Our goal

- https://florafantasy.gucci.com/ <br>
- When moving the mouse to the left or to the right, we can change the position of camera <br>

```javascript
const cursorState = {
  x: 0,
  y: 0,
};

// Size of scene, we can fixed or get full view
const size = {
  width: window.innerWidth,
  height: window.innerHeight,
};

window.addEventListener("mousemove", (e) => {
  // console.log("pos: ", e.clientX, e.clientY);
  cursorState.x = e.clientX / size.width - 0.5;
  cursorState.y = -(e.clientY / size.height - 0.5);
});

// Change position at requestFrame
camera.position.x = cursorState.x * 3;
camera.position.y = cursorState.y * 3;

// We can view it at 0, 0, 0
camera.lookAt(new THREE.Vector3());
```
