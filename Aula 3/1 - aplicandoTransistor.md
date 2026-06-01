# APLICANDO O TRANSISTOR

<p> Um transistor é um dos componentes eletrônicos mais importantes da história moderna — essencialmente, ele é a base de toda a computação e dos chips que rodam nos nossos celulares e computadores. </p> 

<p>Para entender o que ele é e o que ele faz, o jeito mais fácil é dividi-lo em duas funções principais: uma chave liga/desliga e um amplificador. </p> 

## As Duas Funções Principais
### 1. Uma Chave Eletrônica (Interruptor)
<p> Pense em um interruptor de luz na parede da sua casa: você precisa ir lá com o dedo e apertá-lo física e mecanicamente para acender a lâmpada. </p> 

<p> O transistor faz exatamente a mesma coisa, mas sem nenhuma peça móvel. Em vez de usar o seu dedo, você usa um sinal elétrico (uma pequena tensão) para abrir ou fechar o circuito. </p> 

<ul>
  <li>
    Se você aplica uma pequena corrente elétrica no "gatilho" do transistor, ele deixa a corrente principal passar (posição ligado).
  </li>
  <li>
    Se você remove essa corrente, ele barra o fluxo (posição desligado).
  </li>
</ul>
<p> 💡 Como isso cria computadores? No mundo digital, o estado "desligado" representa o número 0 e o estado "ligado" representa o número 1. Ao combinar bilhões de transistores que ligam e desligam bilhões de vezes por segundo, os processadores conseguem fazer cálculos complexos e rodar softwares. </p>

## 2. Um Amplificador de Sinal
<p> O transistor também pode funcionar de forma "parcialmente aberta". Se você enviar um sinal elétrico muito fraco e oscilante para o gatilho dele, ele consegue modular uma fonte de energia muito maior para copiar exatamente aquele desenho de sinal, só que com muito mais força. </p>

<ul>
  <li> É assim que o microfone do seu celular (que gera uma eletricidade minúscula com o som da sua voz) consegue fazer uma caixa de som pesada vibrar bem alto.
  </li>
</ul>

<img width="950" height="850" alt="Shiny Migelo-Maimu" src="https://github.com/user-attachments/assets/7beb013e-4cc8-4b75-a3a2-c67c46f11751" />

<img width="950" height="850" alt="Shiny Migelo-Maimu (1)" src="https://github.com/user-attachments/assets/a9f4d7b1-0024-447b-a028-18fb5c214d28" />

```
void setup()
{
  pinMode(10, OUTPUT);
}

void loop()
{
  digitalWrite(10, HIGH);
  delay(1000); 
  digitalWrite(10, LOW);
  delay(1000); 
}
```
