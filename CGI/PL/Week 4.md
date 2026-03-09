Assignment 2
## Shaders
### Vertex
Corre 1 vez para cada posicao e passa-a para a frente, faz da posicao um vetor de 4 elements da posicao e 1.0
```cpp
layout (location = 0) in vec3 in_position;

void main() {
  gl_Position = vec4(in_position, 1.0);
}
```
### Fragment
Um vetor de 4 valores de cores, RGB. Corre uma vez para cada pixel do vertex shader, que vai determinar se algo é desenhado no ecrã.
```cpp
layout (location = 0) out vec4 out_color;

void main() {
  out_color = vec4(0,1,0,1);
}
```

Em jogos os shaders são compilados em run time, pois são específicos para aquela gráfica.

## Aliasing
Reduz o aspeto "serrado" de sharp edges na renderização 3d através de técnicas de transparência.

## Culling
quando fazemos a transformada do vertex shaders e todo o mundo vai para frente da camera, culling mode agressivo se parte do triangulo tiver fora do ecra n é desenhado. Sem culling mode significa que sao sempre desenhados os objetos mesmo fora de câmera. Por isso num jogo sobem as frames quando escostado a uma parede, o resto do mundo deixa de ser calculado.
