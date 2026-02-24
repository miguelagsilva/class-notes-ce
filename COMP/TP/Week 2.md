*2026-02-16 14:32:18*

Analysis
-------------->
source->Lex->Syn->Sem->Opt->Code Generation->Opt->target
<--------------
Synthesis

C programming language is single pass until the end of the code.

Alphabet in compilers is the whole ascii table or the UTF-8. Lambda in compilers is the epsilon symbol.

###### Tokens
\<natural, 10\> NATURAL(10)
\<if\> IF

![[Pasted image 20260216144113.png]]

Caso hajam prefixos em comum, retira-se o prefixo em todas as ocorrencias e volta a fazer-se.

## Operation Rules
![[Pasted image 20260216144829.png]]

1. Longest Match: Choose the longest substring when two lexical categories are valid
2. Priority for categories: from top to bottom, the first regexps have priority
3. Category for invalids: strings that don't belong to the specified lexical categories.

Regexps and finite automata specify the same languages. AFNDs and AFDs

###### Estado de aceitação: se for estado final de um automato, seja para keyword ou idenficado ou whatever.

![[Pasted image 20260216150122.png]]

## AFND -> AFD
AFND pode estar em multiplos estados ao mesmo tempo
AFD sao subconjuntos do AFND.
![[Pasted image 20260216150726.png]]
![[Pasted image 20260216151356.png]]


AFD vs AFND:
1. n tem lambdas
2. ? mas n se aplica a compiladores
3. n pode haver + de 1 transicao com a mesma leitura

## Geradores de analisadores lexicais
Automatizam a conversão REGEXP → AFND → AFD → Analisador


## TP-01-lr.pdf
1
a) (01|0)* 11 (01|0)* 
b) 