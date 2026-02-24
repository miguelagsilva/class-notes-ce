*2026-02-20 02:24:40*
## Recursive program
A program that calls itself.
1) Base case n=0
$$
\frac{n(n+1)}{2}
$$
2) Inductive hypothesis: Assume that is true for k>0
$$
0+1+\dots+k=\frac{k(k+1)}{2}
$$
3) True for k=>true for k+1

## Proof by mathematical induction:
1. (Base case) True for the base case
2. (Inductive hypothesis) Assume that is true for k
3. (Inductive step) True for k => true for k+1
## Function SQ(n)
Base case:
```js
if n=0 then s=0
```
Recursive case:
```js
else
s=sq(n-1)+2(n-1)+1
return s
```
1) Sq terminates for n>= 0
2) Base case: when n=0 it computes n^2=0
3) Inductive hypothesis: after k-1 calls, it computes (k-1)^2
4) Inductive step: k-1 is True => k is true. After k calls it computes k^2
## Examples
### Problem: Draw a Sierpiński triangle
Make a white 
```python
def triangle(l):
	print triangle
	# Base case
	if l=1:
		return
	# Recursive case
	triangle(l/2)
	triangle(l/2)
	triangle(l/2)
	return
```
### Problem: all squares (modified UVa 155)
```python
function square(x,y,z):
  draw square(x,y,z)
  # base case
  if s/2 <= 1
    return 1
  # recursive case
  else
    return square(x+s/2, y+s/2, s/2) +
    square(x+s/2, y-s/2, s/2) +
    square(x-s/2, y+s/2, s/2) +
    square(x-s/2, y-s/2, s/2) + 1
```
### Problem: Depth First Search (DFS) in a graph G = (V,E)
```python
function DFS(G,u):
  color(u) = gray
  for each {u,v}belogs E and color(v)=white
    DFS(v)
  color(u)=black
```
### Problem: Flood Fill
```js
function FloodFill(x,y,z):
  if color(u[x][y]) = true
    return
  else
    print(u[x][y])
    FloodFill(u,x+1,y)
    FloodFill(u,x-1,y)
    FloodFill(u,x,y-1)
    FloodFill(u,x,y+1)
```
### Problem: All binary strings of size n
0000
1000
0100
...
```python
function string(n,S)
  if n=0
    print(s)
  else
    s[n]=0
    string(n-1,s)
    s[n]=1
    string(n-1,s)
    s[n] = "_"
```

## Knapsack Problems
Given a knapsack with a capacity W and n objects, with Wi, ..., Wn, and value Vi, ..., Vn
Optimization: Find a subset of objects with total weight <= W and maximal total value
Decision: Is there a subset of objects with total weight <= W and total value >= k
## Partition Problems
## Subset sum Problem