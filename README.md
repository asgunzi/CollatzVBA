# CollatzVBA
Implementacao da Conjectura de Collatz - VBA

A Conjectura de Collatz é o problema não resolvido de matemática mais simples da história.

Pegue um número qualquer n.

Se n for par, divida por 2
Se n for ímpar, calcule 3*n+1
E continue fazendo essa conta.

A conjectura diz que a sequência sempre vai convergir para 1.

Exemplo: número inicial 5

5 -> 16 -> 8 -> 4 -> 2 -> 1

Foram 5 passos para convergir para 1.

Exemplo: número inicial 6

6 -> 3 -> 10 -> 5 -> 16 ->  8 -> 4 -> 2 -> 1

Foram 8 passos para convergir para 1.

Para números de 2 a 50, o resultado do número de passos mostra:


Informações interessantes: apesar de extremamente simples de ser formulada, essa conjectura até hoje não foi provada.

É contra intuitivo; parece que vai crescer, mas aí converge.

A sequência é errática: um número pode precisar de 100 passos, o vizinho precisa de 5.

No VBA, a forma mais simples de resolver é com um simples loop while.

Function collatz(n)

Dim count As Long

count = 0
While n > 1

1
2
3
4
5
6
If n Mod 2 = 0 Then
    n = n / 2
Else
    n = 3 * n + 1
End If
count = count + 1
Wend

collatz = count

End Function

Veja também:

https://en.wikipedia.org/wiki/Collatz_conjecture

https://www.quantamagazine.org/why-mathematicians-still-cant-solve-the-collatz-conjecture-20200922/

