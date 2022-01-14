## Textures

### Our goal

- `Mesh` được tạo nên từ `Material (Chất liệu)` + `Geometries (Object vật thể)` <br>

```javascript
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({ color: 0xffff00 });
const mesh = new THREE.Mesh(geometry, material);
scene.add(mesh);
```

