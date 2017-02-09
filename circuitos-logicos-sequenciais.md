# Circuitos Lógicos Sequenciais

## Flip-Flops

A figura a seguir mostra um diagrama em blocos de um sistema digital geral, que reúne portas lógicas combinacionais com dispositivos de memória.

![](/assets/diagrama-geral-sistema-digital.png)

O elemento de memória mais importante é o **flip-flop \(FF\)**, composto por um conjunto de portas lógicas. O conceito de **realimentação** é aplicado sobre um conjunto de portas lógicas de modo a permitir que executem a funcionalidade de armazenamento de informacão. Isso é feito conectando determinadas saídas de porta de volta às entradas de porta apropriadas.

A figura a seguir mostra um tipo de símbolo genérico usado para representar um flip-flop e ele é composto da seguinte forma:

* Saída $$Q$$: chamada de **saída normal**
* Saída $$\overline{Q}$$: chamada de **saída invertida**
* Estado ALTO ou **SET**: quando $$Q=1$$
* Estado BAIXO, **CLEAR** ou **RESET**: quando $$Q=0$$    

![](/assets/flip-flop-simbolo-geral.png)

O conceito de "estado" é importante porque insere o fator **tempo** nos modelos de circuitos. Isso será visto mais adiante.

## Flip-Flop com portas NAND

O Flip-Flop com portas NAND também é chamado **latch com portas NAND** ou simplesmente **latch **e sua composição é ilustrada pela figura a seguir.

![](/assets/ff-com-portas-nand.png)

As duas portas NAND são interligadas de modo cruzado, de modo que a saída da NAND\#1 é conectada a uma das entradas da NAND\#2 e vice-versa.

As entradas SET e RESET funcionam assim:

* quando **SET = RESET = 1** então o FF está em repouso, podendo estar no estado ALTO ou no estado BAIXO
* **SET** e **RESET** são pulsadas exclusivamente \(recebem pulso\) em estado BAIXO para alterar a saída do FF
* quando **SET = 0** então o FF vai para estado ALTO \($$Q=1$$\)
* quando **RESET = 0** então o FF vai para o estado BAIXO \($$Q=0$$\)

Portanto, o estado atual da saída depende do que aconteceu anteriormente nas entrada. Isso explica porque é necessário entender a influência do tempo na formulação desse tipo de circuito lógico.

A partir do estado atual do circuito, podem ser executadas as operações:

* **SETAR** o FF: SET = 0
* **RESETAR** o FF: RESET = 0
* **SETAR e RESETAR** simultaneamente o FF: SET = RESET = 0

As duas primeiras operações são aceitas. Entretanto a última leva o FF ao **estado indesejado**, pois faria com que $$Q = \overline{Q} = 1$$.

A figura a seguir mostra o FF NAND e sua tabela-verdade.

![](/assets/ff-nand-tabela-verdade.png)

Utilizando a ferramenta WaveDrom \(http://wavedrom.com\) informe o código a seguir para gerar um diagrama de tempo do FF NAND. Verifique seu funcionamento.

```
{signal: [
  {name: "SET",   wave: "lhl....hl."},
  {name: "RESET", wave: "l..hlhl..."},
  {name: "Q",     wave: "lh.l...h.."}
]}
```

> Exercício:
>
> Gere o diagrama de tempo das portas AND, OR e NOT.

## Flip-Flop com portas NOR

O Flip-Flop com portas NOR também é chamado **latch com portas NOR** e sua composição é ilustrada pela figura a seguir.

![](/assets/ff-nor.png)

O funcionamento do FF NOR ocorre da seguinte forma:

* quando **SET = RESET = 0** o FF está em repouso e não muda o valor de  $$Q$$
* quando **SET = 1**, o FF vai para o estado ALTO
* quando **RESET = 1**, o FF vai para o estado BAIXO
* quando **SET = RESET = 1**, o FF vai para estado indesejado, pois tenta gerar $$Q = \overline{Q} = 0$$





