# Smooth camera

## Problem

Camera $c$ should follow the Player $p$ smooth. The Player is the final Position the camera should target. For 3D Games the target position could be a fixed distance behind the real Player.

## Solution

### Parameters

- $d$: remaining difference every second
	- between $0$ and $1$
	- $0$ $\to$ $0$% of the difference remains every second ( $c$ is always at the same position as $p$ )
	- $1$ $\to$ $100$% of the difference remains every second ( $c$ does not follow $p$ )
	- $0.5$ $\to$ $50$% of the difference remains every second

### Algorithm

```typescript
parameter d: float //remaining difference per second

variable p: Node3D //Player
variable c: Node3D //Camera

function Update(delta: float) -> void:
	var amount = Power(d, delta) //remaining difference this Update
	c.Position = Lerp(p.Position, c.Position, amount)
	if <3D>:
		//Update the Rotation to be fixed at the player or also follow behind
		c.LookAt(p.Position) or c.Rotation = Lerp(p.Rotation, c.Rotation, amount)
```

## References

[Lerp (Wikipedia)](https://en.wikipedia.org/wiki/Linear_interpolation)

## Notes

Some Tutorials use `C.Position = Lerp(P.Position, C.Position, d)` without `Power`
- if the frame rate is fixed `Power` is not required, because the result is constant
- if the frame rate is variable the result is wrong

The same calculation can be used to interpolate between any values where linear interpolation exists (float, Vector2, Vector3, Quaternion)

## Explanation

Every second the difference $dist$ between $F$ and $T$ should be multiplied by $d$.
$$dist = dist * d$$

If we multiply $dist$ by $a$ every Update we get
$$dist = dist * a * a * ... = dist * a^{fps} = dist * a ^ {\frac{1.0}{delta}}$$
Combined
$$dist * d = dist * a ^ {\frac{1.0}{delta}}$$
Solved for $a$
$$a ^ {\frac{1.0}{delta}} = d$$
$$a = \sqrt[\frac{1.0}{delta}~~~~]{d} = d ^ \frac{1.0}{\frac{1.0}{delta}} = d^{delta}$$
To multiply $a$ with the remaining distance we can use linear interpolation between $T$ and $F$
