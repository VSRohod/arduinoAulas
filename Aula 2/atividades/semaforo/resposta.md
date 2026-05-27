# PEÇAS
<img width="1137" height="568" alt="aula 2" src="https://github.com/user-attachments/assets/b82315b4-9308-41be-839e-f3eb8633f2c9" />

# CÓDIGO
```
int b1 = 2;
int bAtivo1 = 0;
int ledVerde = 13;
int ledAmarelo = 12;
int ledVermelho = 11;


void setup()
{
  pinMode(b1, INPUT);
  pinMode(ledVerde, OUTPUT);
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);
}

void loop()
{
  digitalWrite(ledVerde, HIGH);
  
  bAtivo1 = digitalRead(b1);
  
  if(bAtivo1 == 1){
    digitalWrite(ledVerde, 1);
    delay(2000); 
	digitalWrite(ledVerde, 0);
    
    digitalWrite(ledAmarelo, 1);
    delay(3000); 
	digitalWrite(ledAmarelo, 0);
    
    digitalWrite(ledVermelho, 1);
    delay(7000); 
	digitalWrite(ledVermelho, 0);
  }
  
}

```
