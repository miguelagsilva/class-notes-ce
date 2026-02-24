*2026-02-18 11:42:13*

(vk) is vulkan
(vlk) is vulkan launchpad for learning
() nothing is something else

## Types of geometries:
- Point cloud
- Voxel
- Polygon mesh

Triangle are the simplest forms of geometry, even squares are mawde of triangles. Circles can not be made out of triangles, the more triangles use the closer we get to a curve

## Projections:
- Perspective
- Ortographic/orthogonal
- Fish eye

## Matrices:
Multiply position matrix with P (4 by 4) to get positions, From 3d positions to 2d positions so it can be rendered on the screen. 
Calculations with matrices can be done in 1 clock cycle, so multiple multiplications can be done at once, not like it would be in a CPU.

### Translation:
x' = x+2
y' = y
z' = z

### Rotation:
x' = -x
y' = -y
z' = z

v1,v2,v3 * x  =

| v1  | v2  | v3  |
| --- | --- | --- |
\*

| x   |
| --- |
| y   |
| z   |

= v1\*x + v2\*y + v2*z

So rotation matrix would be 
multiplying the position matrix with this
### Rotation matrix

| -1  |     |     |
| --- | --- | --- |
|     | -1  |     |
|     |     | 1   |

We cant do translations to a particular dimension by multiplying the position with a 3by3 matrix, so we need to make it 4 by 4, in both the multiplier and quarternian vector.

## Quaternian vector
Because of the above reasons our vector needs to be 4 dimensions, the fourth value is w=1.

| x   |
| --- |
| y   |
| z   |
| w=1 |
w is always 1.

Each vertice has its own quaternian vector to indicate its position.

## Projection matrix
we make the w go from the fourth slot to the third.

- Geometry types => Meshes
- Perspective Projection => 4x4
- Translations, Rotations => 4x4
- Quaternians

from vertices to sides

each side has 3 vertices, the points of the triangle.

Light is projected thousands or millions timnes and bounces of surfaces, some of these bounces go into the players camera, to each point there is a certain amount of light that gets there.

V -> Projection (vertex shader, return M.V) -> 2D Controls -> Shading (fragment shader, Is in object return 1,0,0) ->