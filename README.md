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
![](https://ferramentasexcelvba.files.wordpress.com/2020/11/collatz.png)

Informações interessantes: apesar de extremamente simples de ser formulada, essa conjectura até hoje não foi provada.

É contra intuitivo; parece que vai crescer, mas aí converge.

A sequência é errática: um número pode precisar de 100 passos, o vizinho precisa de 5.

No VBA, a forma mais simples de resolver é com um simples loop while.

Function collatz(n)

Dim count As Long

count = 0
While n > 1

If n Mod 2 = 0 Then
    n = n / 2
Else
    n = 3 * n + 1
End If
count = count + 1
Wend

collatz = count

End Function

É possível pensar numa estrutura da dados mais complexa, porém com melhor performance computacional.

Por exemplo, salvar o número de passos de todos os valores já rodados. Rodar a sequência até chegar a um número menor do que o atual, e aí resgatar da memória o resultado já calculado.

![](https://ferramentasexcelvba.files.wordpress.com/2020/11/collatz.jpg)
Com esse método, é possível calcular os primeiros 110 mil números, em menos de 1 segundo.

No VBA, o limite é restrição de tamanho do tipo Long. Não há um tipo Big Int, como em Java ou Python, o que torna bem complicado calcular mais do que isso.


Código no Github: https://github.com/asgunzi/CollatzVBA

Veja também:

https://en.wikipedia.org/wiki/Collatz_conjecture

https://www.quantamagazine.org/why-mathematicians-still-cant-solve-the-collatz-conjecture-20200922/

