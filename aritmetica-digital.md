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





