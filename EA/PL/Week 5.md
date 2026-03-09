*2026-03-09 11:13:31*

Problema D do mooshak
## Top down

Isto prova que o nosso algoritmo é capaz de resolver o problema.
### Subestrutura ótima
- Pressuposto: v\[i,j] é a maior soma
- Negação: v\[i,j] - P\[i,j] -> v\[i-1,j-1] não resulta na maior soma
- Consequência: v\[i-1,j-1] + P\[i,j] > v\[i,j]
- Contradição: 

## Bottom up