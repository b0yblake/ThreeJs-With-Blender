## How t duplicate object
### Our goal

```javascript
// Group object
const group = new THREE.Group();
SCENE.add(group)

const cube1 = new THREE.Mesh(
	new THREE.BoxGeometry( 1, 1, 1 ),
	new THREE.MeshBasicMaterial( { color: 0x13a3f6 } )
)
cube1.position.set(4, -1, 0);
group.add( cube1 );

const cube2 = new THREE.Mesh(
	new THREE.BoxGeometry( 1, 1, 1 ),
	new THREE.MeshBasicMaterial( { color: 0x00ff00 } )
)
cube2.position.y = -1;
group.add( cube2 );
```
