# Aritmética Digital

## Adição e subtração binárias

Revisão da adição de números decimais:

![](/assets/adicao-numeros-decimais-lsd.png)

A operação é realizada da direita para a esquerda, começando do **dígito menos significativo** \(LSD, do inglês _least-significant-digit_\). Quando os dígitos da segunda coluna são somados o resultado é $$7+6=13$$, o que gera o "_vai um"_ \(ou **carry**\) com valor $$1$$, que vai para a próxima coluna e, por fim, gera a soma $$1+3+4=8$$ .

Na **adição binária**, ocorrem os mesmos passos, entretanto, podem ocorrer apenas quatro casos:

* $$0+0=0$$
* $$1+0=1$$
* $$1+1=10$$
* $$1+1+1=11$$

Nos dois últimos casos há a presença do carry de 1 para a próxima posição. Alguns exemplos:

![](/assets/adicaco-binaria-exemplos.png)

Na subtração binária a situação é semelhante e também há quatro situações possíveis para lidar quando subtrair um bit de outro:

* $$0-0=0$$
* $$1-1=0$$
* $$1-0=1$$
* $$0-1=1$$

No último caso ocorre o "tomar emprestado" da próxima coluna. Alguns exemplos:

![](/assets/exemplos-subtracao-binaria.png)

> ## Exercícios
>
> Efetue as operações:
>
> a\) 10110 + 00111
>
> b\) 011,101 + 010,010
>
> c\) 10001111 + 00000001
>
> d\) 101101 - 010010
>
> e\) 10001011 - 00110101
>
> f\) 10101,1101 - 01110,0110

## Representação de números com sinal

Computadores e calculadoras digitais geralmente operam com números negativos e positivos. Assim, é necessário utilizar o _sinal_ do número \($$+$$ ou $$-$$\). Para isso, acrescenta-se ao número outro bit, chamado **bit de sinal**. A convenção é que o valor $$0$$ represente o sinal $$+$$ e o valor $$1$$ represente o sinal $$-$$, o que é ilustrado pela figura a seguir.

![](/assets/representacao-de-numeros-com-bit-de-sinal.png)

Na figura, o primeiro número é 0110100 \(+52\). O bit mais à esquerda \(bit mais significativo\) tem valor 0, sendo usado para reprentar o sinal positivo. O segundo número é 1110100 \(-52\), tendo o bit mais significativo com valor 1 \(negativo\). A magnitude do número é a sua representação sem sinal. Assim, ambos os números possuem a mesma magnitude \(52\). Essa representação é chamada **sistema sinal-magnitude** para números binários com sinal.

A representação do sistema sinal-magnitude não é utilizada na prática, por exigir uma implementação mais complexa dos circuitos. O **sistema complemento de 2** é o mais utilizado.

## Forma do complemento de 1

O complemento de 1 de um número binário é obtido substituindo cada 0 por 1 e cada 1 por 0, como uma operação de inversão \(ou seja, complemento\).

## Forma do complemento de 2

O complemento de 2 de um número binário é obtido tomando o complemento de 1 do número e somando 1 na posição do bit menos significativo, como mostra a figura a seguir.

![](/assets/complemento-de-2-exemplo.png)

Qual o complemento de 2 do número 101100?

## Representando números com sinal usando complemento de 2

A representação de números com sinal usando complemento de dois funciona da seguinte forma:

* **Se o número for positivo: **

  * a magnitude é representada na forma binária direta
  * um bit de sinal 0 é colocado em frente ao bit mais significativo

* **Se o número for negativo:**

  * a magnitude é representada na forma do complemento de 2
  * um bit de sinal 1 é colocado em frente ao bit mais significativo

  A figura a seguir ilustra esse processo.

![](/assets/numeros-com-sinal-com-complemento-de-2.png)

Outras operações e representações:

* extensão de sinal
* negação
* adição e subtração na forma de complemento de 2
* multiplicação
* divisão
* código BCD



