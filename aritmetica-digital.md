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

Nos dois últimos casos há a presença do carry de 1 para a próxima posição.

Alguns exemplos de aplicação da adição:

![](/assets/adicaco-binaria-exemplos.png)

Na subtração binária a situação é semelhante e também há quatro situações possíveis para lidar quando subtrair um bit de outro:

* $$0-0=0$$
* $$1-1=0$$
* $$1-0=1$$
* $$0-1=-1$$

No último caso ocorre o "tomar emprestado" \(**borrow**\) da próxima coluna. Como o número à esquerda é menor do que o número à direita, o resultado é negativo. Por enquanto a representação do número negativo segue a mesma forma intuitiva em base 10: usando o sinal "-".

Um exemplo mais complicado:  $$110 - 101$$. Para encontrar a solução, vamos por partes, da direita para a esquerda:

1. como não podemos calcular $$0-1$$ diretamente, precisamos pedir emprestado da casa anterior, à esquerda. Assim, o primeiro número ficaria: $$1010$$ sendo que o último $$10$$ é visto como um número só, não como duas novas casas no número.
2. fazemos a subtração dos números mais à direita: $$10-1=1$$
3. fazemos a subtração dos números da próxima casa à esquerda: $$0-0=0$$
4. fazemos a subtração dos números da próxima casa à esquerda: $$1-1=0$$
5. o resultado é o número $$001$$ ou $$1$$

O processo de tomar emprestado repete-se sempre que necessário.

Outro exemplo: $$11000-111$$. Novamente, vamos por partes, pelas casas à partir da direita:

1. como o número da casa à esquerda é $$0$$ não podemos tomar emprestado. Então, pedimos emprestado para a outra casa. Essa, por sua vez, também é $$0$$, o que mantém o impedimento. Continuamos para outra casa à esquerda até ser possível tomar emprestado e encontramos o $$1$$ na quarta casa. Então, reescrevemos as casas do número, em ordem: $$1,0,10,0,0$$. Ainda não podemos usar esse número, porque a casa mais à direita ainda tem o valor $$0$$. Continuamos pedindo emprestado \($$1$$ é subtraído da quarta casa e acrescentado na terceira\), resultando em: $$1,0,1,10,0$$. E mais uma vez \($$1$$ é subtrído da : $$1,0,1,1,10$$. Assim temos$$1,0,1,1,10$$. Aí conseguimos subtrair a casa mais à direita: $$10-1=1$$
2. fazemos a subtração do número à esquerda: $$1-1=0$$
3. fazemos a subtração do número à esquerda: $$1-1=0$$
4. como não há mais nada para subtrair, baixamos as duas casas restantes: $$10$$
5. o resultado é o número: $$10001$$

Para checar se o resultado está correto, basta somar o resultado com o segundo número, ou seja: $$10001+111=11000$$

Alguns exemplos de aplicações da subtração:

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

A representação do sistema sinal-magnitude não é utilizada na prática. O **sistema complemento de 2** é o mais utilizado.

## Forma do complemento de 2

O complemento de 2 de um número binário é obtido em dois passos:

1. Substituir cada 0 por 1 e cada 1 por 0, ou seja, inverter o número
2. Adicionar o número 1 na posição do bit menos significativo \(mais à direita\).

Exemplo:

## ![](/assets/complemento-de-2-exemplo.png)

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



