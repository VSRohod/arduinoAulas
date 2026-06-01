# PEÇAS
<img width="1536" height="852" alt="Swanky Elzing (1)" src="https://github.com/user-attachments/assets/6eb599e7-ed2e-457a-b916-1f7820bccb27" />

# CÓDIGO
```
int b1 = 4;
int b2 = 3;
int b3 = 2;
int bLigado1 = 0;
int bLigado2 = 0;
int bLigado3 = 0;
int led1 = 12;
int led2 = 8;
int trava = 0;

void setup(){
  pinMode(b1, INPUT);
  pinMode(b2, INPUT);  
  pinMode(b3, INPUT);

  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);

  Serial.begin(9600);
}

void loop(){
  bLigado1 = digitalRead(b1);
  bLigado2 = digitalRead(b2);
  bLigado3 = digitalRead(b3); 


  if((bLigado1 == 1) && (trava == 0)){
    Serial.println("EQUIPE AMARELA!");
    digitalWrite(led1, 1);
    trava = 1;
  }
  
  if((bLigado2 == 1) && (trava == 0)){
    Serial.println("EQUIPE AZUL!");
    digitalWrite(led2, 1);
    trava = 1;
  }

  if(bLigado3 == 1){
    Serial.println("PRÓXIMA PERGUNTA!");
    digitalWrite(led1, 0);
    digitalWrite(led2, 0);
    trava = 0;
  }
}
```
