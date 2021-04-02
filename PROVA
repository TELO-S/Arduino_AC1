https://www.tinkercad.com/things/fl8Ix57QzHo-epic-luulia/editel

const int vermelho = 5;
const int verde = 6;
const int azul = 7;
int valorSensorLuz  = 5;
int valorSensorTemp = 15;

const int botao1 = 2;
unsigned long lastDebounceTime1 = 0;
const int botaoDelay = 1000;

const int botao2 = 3;
unsigned long lastDebounceTime2 = 0;

void setup(){
  pinMode(A0, INPUT);
  pinMode(A1, INPUT);

  pinMode(vermelho, OUTPUT);
  pinMode(verde, OUTPUT);
  pinMode(azul, OUTPUT);

  Serial.begin(9600);

  Serial.println("AC1 - Meu Primeiro Projeto 2021");
  Serial.println("                           V1.0");
  Serial.println("Grupo: TELOS             ");
}

void loop()
{
  if((millis() - lastDebounceTime1) > botaoDelay && digitalRead(botao1)){
      Serial.println("botao 1 apertado");
    ledVermelho(true);
      lastDebounceTime1 = millis();
  }
  if((millis() - lastDebounceTime2) > botaoDelay && digitalRead(botao2)){
  Serial.println("botão 2 apertado");
    ledVermelho(false);
    lastDebounceTime2 = millis();
  }
  if(getLuminosidade() > 5){
    ledVerde(HIGH);
  }else{
      ledVerde(LOW); 
  } 


  if(getTemperatura() > 15){
    ledAzul(true);
  }else{
      ledAzul(false); 
  }

  delay(10);
}


void ledVermelho(bool estado){
  digitalWrite(vermelho,estado);
}

void ledVerde(bool estado){
    digitalWrite(verde,estado);
}
void ledAzul(bool estado){
    digitalWrite(azul,estado);

}
 
int getTemperatura(){
      int temperaturaC;
    temperaturaC = map(((analogRead(A0) - 20) * 3.04), 0, 1023, -40, 125);
      return temperaturaC;
 
} 

int getLuminosidade(){
      int luminosidade;
    luminosidade = map(analogRead(A1), 6, 619, -3, 10);
      return luminosidade;
   valorSensorLuz  = analogRead(5);



}
