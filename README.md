# FA22_IXD256


*Sun Clock Project Documentation by Oskar Qian*


```
#include "M5CoreInk.h" 

const int ledPin = 10;  // built-in LED
const int sensorPin = 26;
int sensorValue = 0;
int brightnessVal = 0;
const int OutputPin = 32;
int noEmission = 0;
int currentState = noEmission;
int emission = 1;


void setup() {
  //M5.begin();
  pinMode(ledPin, OUTPUT);
  pinMode(sensorPin, INPUT);
  pinMode(OutputPin, OUTPUT);
  
  Serial.begin(9600);
}

void loop() {
  sensorValue = analogRead(sensorPin);
  Serial.print("sensorValue = ");
  Serial.println(sensorValue);
  analogWrite(ledPin, brightnessVal);
  delay(100);

  if (currentState == noEmission) {
      digitalWrite(OutputPin, LOW);

    if (sensorValue < 700)
      currentState = emission;
  }


  if (currentState == emission) {
     digitalWrite(OutputPin, HIGH);

    if (sensorValue >700 )
      currentState = noEmission;
    }
  }

```
_Blade Runner 2049_ 
![Concept Design](thumb-1920-870886.jpg)