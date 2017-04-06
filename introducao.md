# Introdução

Para essa introdução à programação em Arduino vamos utilizar o aplicativo web [http://circuits.io](http://circuits.io). Crie uma conta de usuário e, depois, utilize o **Eletronics Lab**. A figura a seguir ilustra a tela inicial ao criar um novo "lab".

![](/assets/circuitio-lab-inicio.png)

A barra de ferramentas fornece as funcionalidades, nesta ordem:

* rotacionar a tela
* excluir o componente selecionado \(se houver\)
* zoom para encaixar na janela
* desfazer
* refazer
* mostrar editor de código
* adicionar componente
* iniciar simulação

O botão "adicionar componente" exibe o painel de componentes, que mostra os componentes disponíveis. Para inserir um componente basta selecioná-lo da lista e arrastá-lo para conteúdo do lab.

## Projeto 1: Arduino básico

A partir do painel de componentes, insira o componente "Arduino uno".

Usando o botão "code" você acessa o editor de código. O código padrão é apresentado a seguir.

```
int led = 13;

void setup() {
  pinMode(led, OUTPUT);
}

void loop() {
  digitalWrite(led, HIGH);   
  delay(1000);               
  digitalWrite(led, LOW);    
  delay(1000);               
}
```

Clique no botão "Upload & Run". Nesse momento, o código é compilado e enviado para a placa \(o upload\). O lab entra no modo de simulação e apresenta um cronômetro, além do projeto em funcionamento \(em simulação, claro\). A figura a seguir demonstra isso.

![](/assets/lab1-simulation.png)

Para parar a simulação clique no botão "Stop simulation".

Analisando o comportamento da placa, na parte superior há um led identificado por "1". Ele está associado ao "pino 13" e, por causa do código acima, liga, permanece ligado por um segundo, desliga, permanece desligado por um segundo e continua repetindo esse processo.

No código, algumas partes importantes. Primeiro, declaração de variável. A variável `led` é declarada na linha 1. O tipo dela é `int` e seu valor é `13`. Assim a sintaxe é:

```
tipo nome = valor;
```

Na sequência, há duas funções:

* `setup()`: executa uma vez, no início da execução do programa na placa
* `loop()`: executa indefinidamente \(em loop, como seu nome indica\) e só para quando a placa é desligada ou reiniciada \(simulação interrompida\)

Na função `setup()`, na linha 3, é chamada a função `pinMode()`. A função `pinMode()` determina o "modo" de um pino: saída \(`OUTPUT`\) ou entrada \(`INPUT`\). O pino é identificado por um número. No caso do código, o pino `13` está no modo de `OUTPUT`.

Na função `loop()` são chamadas outras duas funções:

* `digitalWrite(pino, tipo)`: usada para ligar \(`HIGH`\) ou desligar \(`LOW`\) um pino. 
* `delay(n)`: usada para fazer a execução pausar ou atrasar por `n` microssegundos.

## Projeto 2: Usando resitor e led

Mantendo o mesmo código do projeto anterior, vamos alterar o hardware, utilizando os componentes led, resistor, fios e uma placa arduino. Monte os componentes na protoboard de forma semelhante à figura a seguir.

![](/assets/projeto-2-hardware.png)

Alguns pontos importantes:

* Há uma ordem para o posicionamento do resistor \(a fita laranja está para a direita\)
* O lado direito do resistor está ligado no pino 13 da placa \(lembrando que ele está no modo de saída\)
* O pino longo do led está ligado no lado esquerdo do resistor
* O pino curto do led está ligado no GND da placa

Mantendo o mesmo código do projeto anterior, inicie a simulação para ver o resultado. Agora é o led que passa a ficar aceso por um segundo, apagado por um segundo e assim por diante.

## Projeto 3: Interação com o usuário por meio de botões

Com base no Projeto 2, adicione mais fios e o componente Pushbutton. Monte o hardware seguindo a figura a seguir.

![](/assets/projeto-3-hardware.png)

O código é modificado para o seguinte:

```
int led = 13;
int button = 2;

void setup() {
  pinMode(led, OUTPUT);
  pinMode(button, INPUT);
}

void loop() {
  if (digitalRead(button) == HIGH) {
    digitalWrite(led, HIGH);
  } else {
    digitalWrite(led, LOW);
  }
}
```

A variável `button` tem o valor `2`, indicando que está associada ao pino 2. Esse pino é definido no modo de `INPUT` \(entrada\).

A função `digitalRead(pino)` retorna o valor de um pino \(`HIGH` ou `LOW`\) conforme a passagem de corrente elétrica por ele.

Compile e faça upload do código para iniciar a simulação. Clique e segure o botão e note o comportamento do led.

