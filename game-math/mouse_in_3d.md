# Mouse Position in Top-Down 3D

## Problem

We know the player clicked at some screen position, but which position in the game world relates to this screen position.

## Solution

### Parameters

- $height$: height of the plane, in which the intersection occurs

### Algorithm

```typescript
parameter height: float //height of the intersection plane

variable camera: Camera3D //camera node
variable mousePosition: Vector2 //current mouse position

function MouseOnPlane(height: float) -> Vector2:
	//direction of the camera ray for this positon
	var cameraNormal = camera.ProjectRayNormal(mousePosition)
	//start of the camera ray for this position
	var cameraOrigin = camera.ProjectRayOrigin(mousePosition)
	//intersection point between the ray and the plane
	var intersection = origin - normal * (origin.y - height) / normal.y
	//intersection.y is always height
	return Vector2(intersection.x, intersection.z)
```

## Notes

The direction of the ray is not checked, if the plane is behind the camera the intersection point is also behind.

## Explanation

- `origin.y - height`: height distance between the ray origin and the plane
- `(origin.y - height) / normal.y`: amount of steps along normal to reach the plane
- ` normal * (origin.y - height) / normal.y`: vector from the camera to the plane
