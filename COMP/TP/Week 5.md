*2026-03-09 02:22:13*
![[Pasted image 20260309142604.png]]

A partir do simbolo inicial de gramatica gerar a sequencia de input. Com base num token de look-ahead fazer a análise sintática. Em FORTRAN existem situações onde são preciso mais de 1 token de look-ahead, mas isso já n acontece, agr é sempre 1.
![[Pasted image 20260309143036.png]]

FIRST; FOLLOW; NULLABLE

## FIRST
Seguimos os símbolos por ordem até chegar aos terminais. 

![[Pasted image 20260309143414.png]]
![[Pasted image 20260309144159.png]]
## FOLLOW
![[Pasted image 20260309144155.png]]

Queremos as gramáticas LL(1)

![[Pasted image 20260309145144.png]]
> Não determinística

![[Pasted image 20260309145319.png]]

## Análise Sintática
![[Pasted image 20260309145931.png]]

![[Pasted image 20260309150102.png]]

Só temos duas ações em cada passo do parsing:
- Shift
  - Lê o próximo símbolo (terminal), lê mais um símbolo e passa-o para a direita.
  - Decisão permanente.
- Reduce
  - Uma produção aplicada ao contrário
  - Pop do lado direito e push do lado esquerdo
  - Coloca na pilha o lado esquerdo dessa produção

![[Pasted image 20260309151444.png]]

