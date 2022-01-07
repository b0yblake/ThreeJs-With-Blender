## How many way to transform the objects (not camera)
### Our goal

- It's quite good to know all of 4 ways to transform the objects: `position` `scale` `rotation` `quaternion` <br>
- 
- 

| Elements     |                                                |
| -------------| :----------------------------------------------|
| 1. Position  | Cung cấp cách điều chỉnh các tọa độ hoặc method để chỉnh tọa độ |
| 2. Scale     | Cung cấp cách điều chỉnh các kích thước scale hoặc method để chỉnh kích thước scale    |
| 3. Rotation  | Cung cấp cách điều chỉnh các thông số lật (lộn vòng) hoặc method để chỉnh thông số lật (lộn vòng)                                               |
| 4.Quaternion |                                                |

### Get start with elements

1. Position: Position mặc định nếu không được set là `(0, 0, 0)`, vật thể sẽ được căn theo góc độ của camera khi chúng ta set `position của camera` <br>

- https://threejs.org/docs/?q=position#api/en/core/Object3D.position <br>
- `Position` của mesh thuộc `Object3D` cho nên nó sẽ áp được các công thức - tính trạng của `Vector3D` https://threejs.org/docs/?q=position#api/en/math/Vector3 <br>
- https://threejs.org/examples/#webgl_geometry_convex <br>

```javascript
const geometry = new THREE.BoxGeometry( 1, 1, 1 );
const material = new THREE.MeshBasicMaterial( { color: 0x13a3f6 } );
const mesh = new THREE.Mesh( geometry, material );
SCENE.add( mesh );

// Mesh position
mesh.position.x = 0;
mesh.position.y = -2;
mesh.position.z = 0.5;

// Mesh position set
mesh.position.set(0, -2, 0.5);

// Mesh length 
console.log('mesh length: ', mesh.position.length())

// Mesh normalize 
console.log('mesh normalize: ', mesh.position.length())

// Add trục tọa độ x, y, z để tham khảo
// AxesHelper
const AxesHelper = new THREE.AxesHelper(3)
SCENE.add(AxesHelper)
```

2. Scale: tương tự như position, scale tự scale object <br>

```javascript
// Mesh scale
mesh.scale.x = 0;
mesh.scale.y = -2;
mesh.scale.z = 0.5;

// Mesh scale set
mesh.scale.set(0, -2, 0.5);
```

3. Rotation: tương tự như scale, rotation tự rotaion chính nó <br>

```javascript
// Mesh rotaion
mesh.rotaion.x = 0;
mesh.rotaion.y = -2;
mesh.rotaion.z = 0.5;

// Mesh rotaion set
mesh.rotaion.set(0, -2, 0.5);

// Mesh reorder
mesh.rotaion.reorder('YXZ')
```

4. Quaternion: 
