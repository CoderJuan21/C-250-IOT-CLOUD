# C-250-IOT-CLOUD

#include "thingProperties.h"
int ledPin = 23;
void setup() {

  Serial.begin(9600);
  pinMode(ledPin, OUTPUT);
 
  delay(1500); 


  initProperties();

  
  ArduinoCloud.begin(ArduinoIoTPreferredConnection);
  
 
  setDebugMessageLevel(2);
  ArduinoCloud.printDebugInfo();
}

void loop() {
  ArduinoCloud.update();
 
  
  
}



void onLedChange()  {
 
  if(led == 1){
    digitalWrite(ledPin, HIGH);
    Serial.println("ON");
  }
  else{
    digitalWrite(ledPin, LOW);
    Serial.println("OFF");
  }
}
