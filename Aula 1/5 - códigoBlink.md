# CÓDIGO BLINK
## PENSANDO COMO ARDUÍNO  
<p> Se você fosse um robô , como você comandaria a piscada do LED? </p>
<p> A resposta é divida em 4 passos: </p>
<ol>
  <li>Acenda o LED.</li>
  <li>Espere um tempo.</li>
  <li>Apague o LED.</li>
  <li>Espere um tempo.</li>
</ol>

## QUAIS VÁRIAVEIS IREMOS USAR?
<p>Para este programa , usaremos duas variáveis: </p>
<ul>
  <li>LED</li>
  <li>TEMPO</li>
</ul>

## A VARIÁVEL LED
<ul>
  <li> Irá receber o valor do endereço do pino do arduino. </li>
  <li> Pode receber valores entre 0 a 13. </li>
  <li> Deve ser configurada como saída do arduino. </li>
  <li> Deve ser declarada antes de usar-la no programa principal. </li>
</ul>

## ARDUÍNO
<p>Temos essa placa de arduino:</p>
<img width="786" height="598" alt="image" src="https://github.com/user-attachments/assets/f9e1bf86-d2bb-48ed-a011-fb5be0c7f8ac" />

### 1. Alimentação e Conectividade (Lado Esquerdo)
<p>- Porta USB (Conector prata grande, superior esquerdo): Serve para duas funções principais: 
  alimentar a placa a partir do computador (5V) e transferir o código (sketch) desenvolvido na IDE do 
  Arduino para o microcontrolador. Ele também permite a comunicação serial entre a placa e o PC.</p>
<p>- Jack de Alimentação DC (Conector preto, inferior esquerdo): Entrada para fontes de alimentação 
  externas (adaptadores AC/DC ou baterias). O recomendado é alimentar por aqui com uma tensão entre 7V e 12V. 
  A placa possui reguladores de tensão internos para reduzir isso para os níveis seguros de operação.</p>
<p>- Botão de Reset (Botão quadrado com topo laranja/vermelho, superior esquerdo): Serve para reiniciar 
  o microcontrolador. Ao ser pressionado, ele limpa a memória temporária e reinicia a execução do programa 
  do zero, sem apagar o código gravado.</p>

### 2. Pinos de Alimentação e Controle (Barra Inferior - "POWER")
<p>- Esta seção gerencia a distribuição de energia para os componentes externos conectados ao Arduino:</p>
<p>- IOREF: Fornece a referência de tensão com a qual os pinos de E/S (Entrada/Saída) da placa operam 
  (no caso do Uno, 5V). Útil para shields identificarem a tensão da placa.</p>
<p>- RESET: Pino conectado diretamente à linha do botão de reset. Permite reiniciar o Arduino externamente 
  através de um sinal lógico.</p>
<p>- 3.3V: Saída de energia regulada em 3.3 Volts. Usada para alimentar sensores e módulos que operam com essa 
  tensão menor.</p>
<p>- 5V: Saída de energia regulada em 5 Volts. É a principal linha de alimentação para a maioria dos componentes 
  externos comuns (sensores, displays, relés).</p>
<p>- GND (Ground / Terra): Os pinos de aterramento da placa. São os pontos de referência zero para o circuito 
  elétrico. Toda corrente que sai precisa voltar por aqui.</p>
<p>- Vin: Pino de entrada de tensão. Pode ser usado para alimentar o Arduino com uma fonte externa 
  (como uma bateria de 9V) diretamente pelos pinos, contornando o Jack DC.</p>

### 3. Pinos de Entrada Analógica (Barra Inferior Direita - "ANALOG IN")
<p>A0 a A5: São 6 pinos que conseguem ler sinais analógicos variáveis (tensões entre 0V e 5V). O Arduino Uno 
  possui um conversor Analógico-Digital (ADC) interno de 10 bits, o que significa que ele transforma esses 
  valores de tensão em números inteiros que vão de 0 a 1023. São ideais para sensores de temperatura 
  (como o LM35), potenciômetros e LDRs (sensores de luz).</p>

### 4. Pinos Digitais (Barra Superior - "DIGITAL")
<p>- Pinos 0 a 13: São pinos que operam de forma binária, trabalhando apenas com estados de TUDO ou NADA 
  (0V para LOW/Falso e 5V para HIGH/Verdadeiro). Eles podem ser configurados tanto para ler um sinal 
  (como um botão) quanto para enviar um sinal (como acender um LED).</p>
<p>- PWM (~3, ~5, ~6, ~9, ~10, ~11): Os pinos marcados com o símbolo de um tio (~) possuem uma função especial 
  chamada Modulação por Largura de Pulso (PWM). Eles conseguem simular saídas analógicas variando a frequência 
  do pulso digital. São usados para controlar a velocidade de motores DC, o brilho de LEDs ou a posição de 
  servomotores.</p>
<p>- TX (1) e RX (0): Pinos dedicados à comunicação serial TTL. RX (Receive) recebe dados e TX (Transmit) 
  transmite. Eles estão conectados internamente ao chip que gerencia a porta USB, por isso evita-se usar esses 
  pinos para outras funções se você estiver comunicando o Arduino com o computador.</p>
<p>- AREF (Analog Reference): Pino de referência de tensão para as entradas analógicas. É usado se você quiser 
  definir um limite superior diferente de 5V para o conversor ADC (por exemplo, usar uma referência externa 
  ultra-precisa de 3.3V).</p>
<p>- GND: Um pino de aterramento adicional para facilitar as conexões na parte superior.</p>

### 5. O Cérebro e Componentes de Suporte
<p>- Microcontrolador Principal (O chip longo preto no centro inferior): É o ATmega328P (em sua versão encapsulada
  DIP de 28 pinos). Ele é o "processador" do Arduino. É onde o seu código fica gravado (na memória Flash) e 
  onde todas as operações lógicas, matemáticas e de controle são executadas de fato.</p>
<p>- Cristal Oscilador / Oscilador de Cristal (Componente metálico ovalado SPK16.000G): É o "coração" ou o 
  relógio da placa. Ele dita o ritmo de trabalho do microcontrolador, oscilando exatamente a 16 MHz 
  (16 milhões de ciclos por segundo). É o que garante a precisão de tempo nas funções do código.</p>
<p>- Microcontrolador Auxiliar / Conversor USB-Serial (Chip quadrado menor, próximo à porta USB): Gerencia a 
  comunicação entre o computador (interface USB) e o processador principal (interface Serial). Ele traduz os
  dados que vêm do PC para que o ATmega328P consiga entendê-los na hora do upload do código.</p>
<p>- LEDs Indicadores (Próximos ao centro e à direita):</p>
<ol>
  <li>ON: LED que indica se a placa está energizada (ligada).</li>
  <li>TX e RX: Piscam rapidamente quando há transmissão ou recepção de dados pela porta USB (como no momento em que 
você carrega um código).</li>
  <li>L: Um LED integrado conectado internamente ao Pino Digital 13. Ele serve para testes rápidos, permitindo 
que você teste códigos (como o clássico "Blink") sem precisar montar circuitos externos.</li>
</ol>

## EXEMPLO
<p> Aqui temos um arduino, e um led com um resistor, o led pode ser conectado a qualquer
  slot , porém o resistor é importante para justarmente ajustarmos a corrente para ele não explodir!</p>
<img width="766" height="380" alt="image" src="https://github.com/user-attachments/assets/7c92b1a9-73d6-416c-92cf-ebe15afd53ec" />
<p> Observe que temos dois pinos no led , Ânodo (pino positivo) de onde deverá vir a energia e Cátodo (pino negativo) de onde deve devolver a energia 
  ( Ou seja, GND ), deixe as conecções exatamente assim:</p>
<img width="546" height="308" alt="image" src="https://github.com/user-attachments/assets/7794b78d-b228-4026-8b5a-cd7582d35e7c" />
<p>Para de fato fazermos o led piscar iremos inserir o código a abaixo, com isso de meio e meio segundo o led 
ficará piescando! </p>
<img width="970" height="642" alt="image" src="https://github.com/user-attachments/assets/b4b222a9-3a02-434a-b952-95a9af4c1783" />
<p>Quando temos esse exemplo montado, podemos observar que o HIGH sempre vai nos trazer uma voltagem próxima a 5v , quando LOW , ele será 0, segue a montagem + código: </p>
<img width="991" height="739" alt="Stunning Leelo-Maimu" src="https://github.com/user-attachments/assets/51f5717b-ae8b-4c8d-98f1-ebbaa2fc505f" />

```
// DECLARAÇÃO DE VARIÁVEIS
int LED = 3;
int tempo = 500;

// CONFIGURAÇÕES INICIAIS
void setup(){
  pinMode(LED, OUTPUT);
}

// PROGRAMA PRINCIPAL
void loop(){
  digitalWrite(LED, HIGH); // ACENDER LED
}

// FIM DO PROGRAMA


```

