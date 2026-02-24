### 1)  (ficha2)
1) Caso base
2) Hipótese Indutiva
3) Passo indutivo

n!>3^n , n>=7
1) $$n=7: 7!> 3^7$$
2) $$ 7<=k<n, k!>3^k $$
3) $$ n=k+1, (k+1)!>3^(k+1) $$
### 2) (ficha2)
```python
Function F(n):
  if n=0 then s=1
  else s=n * F(n-1)
  return s
```
1) n=0 -> s=1 0!=1
2) n=k-1 -> s=(k-1)!
3) n=k -> s=k\*F(k-1) => s=k*(k-1)! = k!

### A new chess game
Inputs:
- x,y,m cavalo
- N cavalos
Outputs:
- nr de celulas distintas
Restricoes:
- tipo de movimento
- n de movimentos

```python
map<int,int> mp = {};
int counter = 0;
function chess(x,y,m):
    int v=0;
	if m <= 0: return v;
	if mp[x][y] == False: 
	  mp[x][y] = True;
	  v=1
	return chess(x-2, y+1, m-1) +
	chess(x-1, y+2, m-1) +
	chess(x+1, y+2, m-1) +
	chess(x+2, y+1, m-1) +
	chess(x-2, y-1, m-1) +
	chess(x-1, y-2, m-1) +
	chess(x+1, y-2, m-1) +
	chess(x+2, y-1, m-1) + v
```

### 3) (ficha2)
1) Caso base: n=1: sequencia ordenada
2) Hipótese Indutiva: Se ordenado n=k 1<k<\n
3) Caso indutivo: Entao ordenado para n=k+1

