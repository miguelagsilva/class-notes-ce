## Agents

### Comportamento
Comportamento em geral do agente. ex: avanca para em frente e come comida sempre que a encontra.
### Percepcoes
- ha comida em frente?
### Acoes:
- avancar para a frente
- comer a comida
### Memoria:
- comeu ou nao na iteracao anterior

### Limitações Agentes Reativos
- Nao ha planeamento


### Agentes Reativos
Mapeia percepcoes -> acoes
Pode usar memoria simples.
O comportamento global ano esta explicitamente representado
Resulta da aplicacao iterativa das regras

## Ficha de Agentes Reactivos 2026
### 1. Hercos
Percepcoes:
- O: Deteta presenca de obstaculos
Acoes:
- A: avancar para a frente
- E: virar 90graus para esquerda
- D: virar 90 graus para direita
Memoria:
- M = \[A\] -> memoriza que avanca
- M = \[E] -> memoriza que rodou a esquerda
- M = \[D] -> memoriza que rodou a direita
Sistema de Producao:
- M\[A]: ~O -> A    (n é necessário M=\[A] pois já está assim)
- M\[A]: O -> D, M=\[D] 
- M\[D]: O -> D
- M\[D]: ~O -> A, M\[A]

Geral: Anda em frente quando n tem obstáculo e quando há obstáculo vira à direita até não ter nenhum

### 5. Covardex
Percepções: 
- Ec: sua energia
- Ea: energia agente
- O: agente em frente
Ações:
- A: Avançar em frente
- D: Rodar 90 graus para direita
- E: Rodar 90 graus para esquerda
- Ge: Ganhar energia
- Pe: Perder energia
Memória:
- N/A
Sistema de Produção:
 - ~Ec -> Nil
 - Ec, ~A -> Av, Pe
 - Ec, A, Ec\<Ea -> D,Pe
 - Ec, A, Ec\>Ea -> Av, C, Ge, Pe2