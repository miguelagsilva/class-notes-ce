V && P-> vertex shader (P.V) -> F -> fragment shader () -> I

## Classic Rasterization (OpenGL)
Application -> Geometry Processing -> Rasterization -> Pixel processing

## Types of Projection
- parallel preserves relative proportion

    x y z 1
x  *  1 2 3 4 = x'
y                     y'
z                     z'
1                      1

y'=x+2y+

## View matrix
constante para tudo, translacoes, rotacoes... matrix da camera

> Projection matrix * View Matrix = Projection view matrix

Because of the above it is the same if we rotate the world or rotate the camera.

## Model matrix
como a view matrix mas para um modelo

P.V.M1\*x1
P.V.M2\*x2

Existe uma hierarquia de model matrixs,
Body
 - Arm1
   - Hand1 
 - Arm2
   - Hand2
As manipulacoes sao feitas da ponta para cima pela arvore. Multiplica pelo Hand1, pelo Arm1, pelo Body1.

Example: Gets on a bus we add the multiplication of the bus as well, now he walks the same but on top of the bus

## Shaders
Language GLSL

Vertex shader: basic.vert
```c
#version 450
layout (location = 0) in vec3 in_position;

void main() {
	gl_position = vec4(in_position, 1.0)
}

float getRecked(float v) {
	return 1.0;
}
```

Fragment shader: frag.vert
```c
#version 450
layout (location = 0) out vec4 out_color;

void main() {
	out_color = vec4(1,1,1,1)
}
```

Trabalho 4 para a frente, sao mais shaders