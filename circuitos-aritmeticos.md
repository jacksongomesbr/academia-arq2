# Circuitos Aritméticos

Computadores e calculadoras digitais utilizam flip-flops combinados para somar, subtrair, multiplicar e dividir números binários.

## Unidade lógica e aritmética

Em um computador, as operações lógicas e aritméticas são realizadas na unidade lógica e aritmética \(ALU, do inglês _arithmetic/logic unit_\). A figura a seguir ilustra uma ALU.

![](/assets/alu-blocos-funcionais.png)

O principal objetivo da ALU é receber dados binários armazenados na memória e executar operações lógicas e aritméticas sobre eles, conforme instruções provenientes da **unidade de controle**. A ALU contém pelo menos dois registradores: **registrador B** e **registrador acumulador**. Uma sequência de operações pode ocorrer da seguinte maneira:

1. a unidade de controle recebe as instruções \(provenientes da **unidade de memória**\) indicando que um número \(armazenado em um endereço de memória\) será somado ao número armazenado no registrador acumulador
2. o número a ser somado é transferido da memória para o registrador B
3. os números do registrador B e do registrador acumulador são somados no **circuito lógico** e o resultado da soma é enviado ao registrador acumulador
4. o novo número no registrador acumulador pode ser mantido nele \(para outras operações\) ou armazenado na memória

## Somador binário paralelo





