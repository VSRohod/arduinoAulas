# CONDICIONAL DUPLO
<p> Quando trabalhamos com mais de uma verificação temos que utilizar dos "&&"(AND) e "||"(OR) e nisso podemos avançar mais em alguns projetos avançados como este que anteriormente executamos, porém com mais de um botão :</p>

<img width="1912" height="851" alt="Copy of aula 2 - arduino" src="https://github.com/user-attachments/assets/7ff5de0c-aeb1-4c73-a4b9-5ec18245d27f" />

```
int botao1 = 5;
int botao2 = 3;
int estado_botao1 = 0;
int estado_botao2 = 0;

int LED = 6;


void setup(){
  pinMode(botao1 , INPUT);
  pinMode(botao2 , INPUT);
  pinMode(LED, OUTPUT);
}

void loop(){
  estado_botao1 = digitalRead(botao1);
  estado_botao2 = digitalRead(botao2);
  
  if((estado_botao1 == 1) && (estado_botao2 == 1) ){
    digitalWrite(LED, HIGH);
  }else{
    digitalWrite(LED, LOW);
  }
}
```

