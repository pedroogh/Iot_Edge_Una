# Trabalho para avaliação do curso de Iot.
 Aluno: Pedro Henrique de Oliveira Gomes
 
 Foi feita a montagem de um circuito com arduino, no Software Tinkercad onde faz a simulação de um semáforo com LCD e Buzzer para informar quando o pedestre pode atravessar, quando não pode e quando deve ter cuidado para isso usei buzzers com tons diferentes.
  
 Segue abaixo um print da montagem no tinkercad:
 ![image](https://user-images.githubusercontent.com/111025893/193410311-39c14b1c-1c62-46ab-9905-b06abdbacc14.png)
  
  
 Segue abaixo o código escrito:
 
 // C++ code
#include <Adafruit_LiquidCrystal.h>
Adafruit_LiquidCrystal lcd_1(0);

void setup()
{
  pinMode(13, OUTPUT);
  lcd_1.begin(16, 2);
  pinMode(12, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(11, OUTPUT);
}

void loop()
{
  
  digitalWrite(13, HIGH); // Acendo o LED Vermelho.
  lcd_1.print("Atravesse"); // Indico que o pedestre pode atravessar.
  int buzzer = 0; // Declaro uma variável para tocar o buzzer.
  while(buzzer<7){ // Toco o buzzer durante 19 segundos.
  	tone(8,1000);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,1200);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,800);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,1000);
  	delay(200);
  	noTone(8);
  	delay(500);
    buzzer++;
  }
  lcd_1.clear(); // Desligo o LCD
  digitalWrite(13, LOW); // Desligo o LED
  digitalWrite(12, HIGH);// Acendo o LED Amarelo.
  lcd_1.print("Cuidado !");// Indico que o pedestre para ter cuidado ao atravessar.
  buzzer = 0;//Zero o buzzer para reiniciar a contagem do while.
  while(buzzer<7){ // Toco o buzzer em tons diferentes durante 19 segundos.
  	tone(8,900);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,1200);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,500);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,1000);
  	delay(200);
  	noTone(8);
  	delay(500);
   buzzer++;
  }
  lcd_1.clear();// Desligo o LCD
  digitalWrite(12, LOW);// Desligo o LED
  digitalWrite(11, HIGH);// Acendo o LED Verde.
  lcd_1.print("Nao atravesse");// Indico que o pedestre não pode atravessar.
  buzzer = 0;//Zero o buzzer para reiniciar a contagem do while.
  while(buzzer<7){ // Toco o buzzer em tons diferentes durante 19 segundos.
  	tone(8,800);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,1000);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,600);
  	delay(200);
  	noTone(8);
  	delay(500);
  	tone(8,1000);
  	delay(200);
  	noTone(8);
  	delay(500);
    buzzer++;
  }
  digitalWrite(11, LOW);// Desligo o LED
  lcd_1.clear();// Desligo o LCD
}

Segue abaixo o link do tinkercad para simulação:
 https://www.tinkercad.com/things/1fPdC3hgAgO-semaforo-com-buzzer-e-lcd-/editel?sharecode=2BruPMiyeW-CrKVXtvovLA_YivVhvZWf96hr1ffJIbo
