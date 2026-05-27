# CONDICIONAL ARDUINO
<p> Quando trabalhamos com arduino também podemos trabalhar condicionais para verificar status e a partir disso
escolher que tipo de comportamentos queremos!</p>
<p> Um dos exemplos mais aplicados é o seguinte, queremos configurar um botão no arduíno que ao pressionar-lo
o led ligará , mas para isso vamos dar a voltagem de 5v para o botão e conectar os pinos das peças, logo em 
seguida utilizado o código listado a baixo: </p>

<img width="991" height="739" alt="Stunning Leelo-Maimu (2)" src="https://github.com/user-attachments/assets/06843c71-81c0-4755-b54b-db786e6a8afb" />

```
int botao = 6;
int LED = 8;
int estado_botao = 0;

void setup(){
  pinMode(botao, INPUT);
  pinMode(LED, OUTPUT);
}

void loop(){
  estado_botao = digitalRead(botao);
  
  if(estado_botao == 1 ){
	digitalWrite(LED, HIGH);
  }else{
	digitalWrite(LED, LOW);
  }
  
}
```
<p>Também podemos rodar if sem else como segue o próximo código a seguir que fará ele ficar piscando :</p>

```
int botao = 6;
int LED = 8;
int estado_botao = 0;
int tempo = 500;

void setup(){
  pinMode(botao, INPUT);
  pinMode(LED, OUTPUT);
}

void loop(){
  estado_botao = digitalRead(botao);
  
  if(estado_botao == 1 ){
	digitalWrite(LED, 1);
    delay(tempo);
    digitalWrite(LED, 0);
    delay(tempo);
    digitalWrite(LED, 1);
    delay(tempo);
    digitalWrite(LED, 0);
    delay(tempo);
  }
  
}

```

