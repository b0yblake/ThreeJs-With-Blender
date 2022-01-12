## Control scene: fullscreen or resizing

### Our goal

1. `Fit the viewport` (Scence === viewport device) <br>

```javascript
// Size of scene, we can fixed (unit px)
const size = {
  width: 800,
  height: 600,
};

// Size of scene, we can get full view (unit 100%)
const sizeOfViewport = {
  width: window.innerWidth,
  height: window.innerHeight,
};
```

- 1 số vấn đề cần quan tâm: `padding-margin` & `Position` <br>

```css
body,
html {
  margin: 0;
  padding: 0;
  overflow: hidden;
}

#webgl {
  position: absolute;
  top: 0;
  left: 0;
  outline: none;
}
```

2. `Handle resize`: Khi render lần đầu, scence fixed kích thước và khi resize browser, hàm render không được chạy lại => lỗi <br>

```javascript
window.addEventListener("resize", () => {
  // console.log("window resizing");

  // When resizing:
  // 1. We update the width & height of scence
  size.width = window.innerWidth;
  size.height = window.innerHeight;

  // 2. Update the camera ratio
  camera.aspect = size.width / size.height;
  camera.updateProjectionMatrix();

  // 3. Update renderer
  renderer.setSize(size.width, size.height);
});
```

3. `Handle the pixelRatio of screen` <br>

```javascript
window.addEventListener("resize", () => {
  // 4. Update renderer ratio
  renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
});
```

4. `Handle the fullscreen` <br>

- https://perimeterx.github.io/map-events-website/ <br>

```javascript
window.addEventListener("dblclick", () => {
  // ...
});
```
