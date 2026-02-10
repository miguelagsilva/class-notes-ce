*2026-02-09 02:54:03*
## Compilers
A progrsm that reads another program written in the source programming language and translates it into another target language. During the compiling it reports any errors that happen.

![[Pasted image 20260209081711.png]]

### Analysis
- Lexical (words in the language)
- Syntatic (correct order of words)
- Semantic (gives meaning to a program, types, variables, functions)

![[Pasted image 20260209082111.png]]

Assembler: assembly -> binary

![[Pasted image 20260209083217.png]]

VHDL to silicon

These TTPs (Lexical, Syntax, Semantics) can be used in many applications such as:

![[Pasted image 20260209084117.png]]

## Evaluation
![[Pasted image 20260209084346.png]]

## Phases
- Analysis
    Text -> Lexical -> Syntatic -> Semantic 
- Synthesis
    -> Machine independent Optimization (not going to be implemented by us) -> Code Generation -> Machine dependent optimization -> ASM/IR

TP Class is 2 weeks ahead of PL
## Final Project
Lexical p1 p2 (14/mar) Tokens
Syntetic p3 p4 (11/abr) AST (syntatic tree)
Semantic p5 (24/abr) AST + tables (notes on each node)
Code gen p6 (9/mai)
LLVM IR (intermediate representation)

![[Pasted image 20260209091535.png]]
![[Pasted image 20260209091546.png]]
![[Pasted image 20260209091556.png]]
![[Pasted image 20260209091603.png]]
![[Pasted image 20260209091612.png]]
![[Pasted image 20260209091625.png]]

Pratical exercises comes from here
https://github.com/rbbarbosa/Petit/

## Lexical Analysis in depth
Divides the code from left to right into its lexical symbols (tokens)

```
if (a==b)
  c=1;
else
 c=0;
```
Turns into
`\tif (a==b)\n\t\tc=1;\n\telse\n\t\tc=0;`

each token (lexical symbol) has a category: keywords, identifiers, operators, numbers, white spaces, specific classes for () = ;
naturals are not empty strings made of only numbers eg: 0, 52, 007, 00

![[Pasted image 20260209094212.png]]


![[Pasted image 20260209094150.png]]

regexp -> non deterministic automata ->  deterministic automata -> table double entry

![[Pasted image 20260209094538.png]]