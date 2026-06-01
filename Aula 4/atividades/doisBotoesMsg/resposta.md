# PEÇAS
<img width="1536" height="852" alt="Swanky Elzing" src="https://github.com/user-attachments/assets/f1a45091-04e5-47d7-a541-83e314ff9830" />

# CÓDIGO
```
int b1 = 11;
int b2 = 10;
int bLigado1 = 0;
int bLigado2 = 0;
int led = 7;

void setup(){
  pinMode(b1, INPUT);
  pinMode(b2, INPUT);
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop(){
  bLigado1 = digitalRead(b1);
  bLigado2 = digitalRead(b2); 

  if((bLigado1 == 0) && (bLigado2 == 0)){
    digitalWrite(led, 0);
  }

  if((bLigado1 == 0) && (bLigado2 == 1)){
    Serial.println("LED ligado");
    digitalWrite(led, 1);
  }

  if((bLigado1 == 1) && (bLigado2 == 0)){
    Serial.println("Velocidade 1");
    digitalWrite(led, 1);
    delay(200);
    digitalWrite(led,0);
    delay(200);
  }

 if((bLigado1 == 1) && (bLigado2 == 1)){
    Serial.println("Velocidade 2");
    digitalWrite(led, 1);
    delay(500);
    digitalWrite(led,0);
    delay(500);
  }
}
```
