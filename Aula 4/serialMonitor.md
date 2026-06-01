# SERIAL MONITOR
<p> Praticamente seria nosso " terminal " do arduino, tudo que e necessario , apenas colocar a quantidade de 
  bits corretamente na variavel serial e montar o algoritmo!  </p>
  
<img width="921" height="742" alt="Neat Curcan" src="https://github.com/user-attachments/assets/7283caf4-61aa-4220-9673-97c40a95c261" />

```
int botao = 11;
int estado = 0;
int led = 7;

void setup()
{
  pinMode(led, OUTPUT);
  pinMode(botao , INPUT);
  Serial.begin(9600);
}

void loop()
{
  estado = digitalRead(botao);
  
  if(estado == 1){
    digitalWrite(led,1); 
    Serial.print("LED LIGADO");
    Serial.print("\n");
    delay(300);
  } else {
  	digitalWrite(led,0); 
  }
  
}
```
<p> Nesse processo podemos por exemplo acrescentar bem mais passos tornando nossas respostas no serial
mais interessantes. </p>

<img width="921" height="742" alt="Neat Curcan (1)" src="https://github.com/user-attachments/assets/6384137c-a415-4a11-bf59-a26a643eea1e" />


```
int botao1 = 11;
int estado1 = 0;
int botao2 = 10;
int estado2 = 0;
int led = 7;

void setup()
{
  pinMode(led, OUTPUT);
  pinMode(botao1 , INPUT);
  pinMode(botao2 , INPUT);
  Serial.begin(9600);
}

void loop()
{
  estado1 = digitalRead(botao1);
  estado2 = digitalRead(botao2);
  
  if(estado1 == 1){
    digitalWrite(led,1); 
    Serial.println("LED LIGADO");
    delay(300);
  } if(estado2 == 1){
    digitalWrite(led,0); 
    Serial.println("LED DESLIGADO");
    delay(300);
  }
  
}
```<img width="921" height="742" alt="Neat Curcan (1)" src="https://github.com/user-attachments/assets/76704d34-4f12-4a97-b3e6-c9bdbc9a6c4c" />
