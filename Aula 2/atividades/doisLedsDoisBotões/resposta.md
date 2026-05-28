# PEÇAS

<img width="950" height="850" alt="Copy of aula 2 - arduino (1)" src="https://github.com/user-attachments/assets/85cea400-0f52-49a8-98e7-0d776432d976" />

# CÓDIGO
```
int botao1 = 5;
int botao2 = 3;
int estado_botao1 = 0;
int estado_botao2 = 0;

int LED1 = 12;
int LED2 = 8;


void setup(){
  pinMode(botao1 , INPUT);
  pinMode(botao2 , INPUT);
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
}

void loop(){
  estado_botao1 = digitalRead(botao1);
  estado_botao2 = digitalRead(botao2);
  
  if(estado_botao1 == 1){
  	digitalWrite(LED1, 1);
    digitalWrite(LED2, 0);
  }
  if(estado_botao2 == 1){
  	digitalWrite(LED2, 1);
    digitalWrite(LED1, 0);
  }
}
```
