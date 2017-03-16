# Circuitos Aritméticos

Computadores e calculadoras digitais utilizam flip-flops combinados para somar, subtrair, multiplicar e dividir números binários.

## Unidade lógica e aritmética

Em um computador, as operações lógicas e aritméticas são realizadas na unidade lógica e aritmética \(ALU, do inglês _arithmetic/logic unit_\). A figura a seguir ilustra uma ALU.

![](/assets/alu-blocos-funcionais.png)

O principal objetivo da ALU é receber dados binários armazenados na memória e executar operações lógicas e aritméticas sobre eles, conforme instruções provenientes da **unidade de controle**. A ALU contém pelo menos dois registradores: **registrador B** e **registrador acumulador **\(também pode ser chamado **registrador A**\). Uma sequência de operações pode ocorrer da seguinte maneira:

1. a unidade de controle recebe as instruções \(provenientes da **unidade de memória**\) indicando que um número \(armazenado em um endereço de memória\) será somado ao número armazenado no registrador acumulador
2. o número a ser somado é transferido da memória para o registrador B
3. os números do registrador B e do registrador acumulador são somados no **circuito lógico** e o resultado da soma é enviado ao registrador acumulador
4. o novo número no registrador acumulador pode ser mantido nele \(para outras operações\) ou armazenado na memória

## Somador binário paralelo

Computadores e calculadoras digitais realizam operações de adição sobre dois números binários de cada vez \(cada um podendo ter vários dígitos binários\). A figura a seguir ilustra a adição de dois números de cinco bits.

![](/assets/processo-adicao-binaria.png)

Em cada passo do processo de adição, três bits são somados: o bit da 1a. parcela, o da 2a. parcela e o carry \(proveniente da posição anterior\). O resultado da adição produz dois bits: um da soma e um de carry \(que será somado aos bits da próxima posição\). O circuito da figura a seguir mostra como esse processo pode ser repetido.

![](/assets/somador-paralelo-diagrama-de-blocos.png)

As variáveis $$A_4, ..., A_0$$ representam os bits da 1a. parcela armazenados no registrador acumulador. As variáveis $$B_4,..., B_0$$ representam os bits da 2a. parcela armazenados no registrador B. As variáveis $$C_4,...,C_0$$ representam os bits de carry. As variáveis $$S_4,...,S_0$$ são os bits de saída do resultado para cada posição\).

Os bits correspondentes à 1a. e 2a. parcela são enviados para um circuito lógico chamado **somador completo** \(FA, do inglês _full adder_\) com um bit de carry da posição anterior.

A figura anterior demonstra como o ciruito pode somar números de cinco bits, mas computadores modernos geralmente trabalham com números de 64 bits.

O circuito em questão é chamado **somador paralelo** porque todos os bits relativos às parcelas são colocados simultaneamente na entrada do somador.

## Projeto de um somador completo

A figura a seguir mostra a tabela-verdade de um somador completo, com três entradas: $$A,B,C_{IN}$$ e duas saídas $$S,C_{OUT}$$. Há, portanto, oito casos possíveis, cada qual relacionado com o valor da saída desejada.

![](/assets/somador-completo-tabela-verdade.png)

A figura a seguir mostra o diagrama de bloco do somador completo.

![](/assets/somador-completo-diagrama-de-blocos.png)

Por exemplo, vamos analisar o caso em que $$A=1,B=0,C_{IN}=1$$. O somador completo \(FA\) tem de somar esses três bits parar gerar $$S=0,C_{OUT}=1$$.

A expressão para a saída $$S$$ é a seguinte:


$$
S=\overline{A}\overline{B}C_{IN}+\overline{A}B\overline{C_{IN}}+A\overline{B}\overline{C_{IN}}+ABC_{IN}
$$


A expressão pode ser simplificada para:


$$
S = \overline{A}(\overline{B}C_{IN} + B\overline{C_{IN}}) + A(\overline{B}\overline{C_{IN}}+BC_{IN})
$$


Utilizando outras operações e simplificações, temos, por fim:


$$
S = A \oplus (B \oplus C_{IN})
$$


A saída $$C_{OUT}$$ é expressa pela equação:


$$
C_{OUT} = AB + AC_{IN} + BC_{IN}
$$


A figura a seguir apresenta o diagrama de circuitos para o somador completo.

![](/assets/somador-completo-circuito.png)

Outros circuitos:

* meio-somador \(HA, do inglês _half adder_\)
* subtrator completo \(FS, do inglês _full subtractor_\)
* meio-subtrator \(HA, do inglês _half subtractor_\)



