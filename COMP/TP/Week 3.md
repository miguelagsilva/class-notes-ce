## Syntatic Analysis (Parsing)
Determines if the program respects the syntax of the language eg. correctly order the lexical symbols.
Input: Sequence of lexical symbols (tokens from last phase)
Output: Syntatic tree of the program, if there are no syntatic errors.
![[Pasted image 20260223142401.png]]
### Example 
square(integer n) = n\*n
Each interior node are an operation and their children are the arguments

Regular expressions are not enough to get the correct order of symbols.

![[Pasted image 20260223142346.png]]
## Context free grammar
- Terminal (T) - the tokens
- Non terminal (NT) - syntatic variables used in productions that represent groups of sequences. 1 or more symbols
- Initial symbol - Non terminal symbol that starts the grammar
- Productions - Substitution rules NT -> (NT U T)* in which the left side can be replaced by the right side

![[Pasted image 20260223142944.png]]
## Example: Grammar of arithmetic expressions
![[Pasted image 20260223143435.png]]
## Derivation
From any phrase that starts with initial symbol we replace any non terminal symbol for the right side recursively until there are no non terminals.

>  Syntax defines ordering, ordering is made with context free grammar 

![[Pasted image 20260223144252.png]]

The leaves of the tree in order, left top bottom, we get the order of the string.
## Ambiguity
![[Pasted image 20260223144845.png]]
## Remove ambiguities
![[Pasted image 20260223150136.png]]
- Levels of priority according to precendece of operators, () * / + -
- Have preferential associativity left to right
- So we introduce non terminal for terms and factors.

> Associativa à esquerda, significa que não é associativa então impusemos uma ordem de avaliação arbitrária esquerda para direita.

![[Pasted image 20260223150949.png]]

O EOF em unix é um \n sem nada à frente

![[Pasted image 20260223151411.png]]

![[Pasted image 20260223151827.png]]

![[Pasted image 20260223152308.png]]

![[Pasted image 20260223152705.png]]

Fazemos a transformação da gramática para criar uma gramática backtrack free que diminui o custo de computação dramáticamente.

![[Pasted image 20260223154233.png]]

Permite construir uma árvore com apenas uma passagem da esquerda para a direita.