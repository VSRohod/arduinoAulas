# PEÇAS
<img width="1536" height="801" alt="Swanky Hango-Krunk" src="https://github.com/user-attachments/assets/ff597565-5b1f-4d35-ab81-b93c9ed1c367" />

# CÓDIGO
```
int b1 = 3;
int b2 = 2;
int bLigado1 = 0;
int bLigado2 = 0;
int led = 11;

void setup(){
  pinMode(b1, INPUT);
  pinMode(b2, INPUT);
  pinMode(led, OUTPUT);
}

void loop(){
  bLigado1 = digitalRead(b1);
  bLigado2 = digitalRead(b2); 
  if(bLigado1 == 1){
    digitalWrite(led, 1);
  }
  if(bLigado2 == 1){
    digitalWrite(led, 0);
  }
}
```
