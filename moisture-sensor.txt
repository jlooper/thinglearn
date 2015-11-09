int sensorPin = A0;
int led = 13;
int thresholdUp = 400;
int thresholdDown = 250;

void setup(){
  Serial.begin(9600);
  pinMode(led, OUTPUT);
}

void loop(){
  
  int sensorValue;
  String DisplayWords;
  
  sensorValue = analogRead(sensorPin);
  
  Serial.println(sensorValue);
  
  if (sensorValue <= thresholdDown){
      
      DisplayWords = "This plant is thirsty!";
      digitalWrite(led, HIGH);   // turn the LED on (HIGH is the voltage level)
        delay(1000);              // wait for a second
      digitalWrite(led, LOW);    // turn the LED off by making the voltage LOW
        delay(1000); 
      Serial.print(DisplayWords);
  
  } else if (sensorValue >= thresholdUp){ 
      
      DisplayWords = "This plant is A-OK!";  
      Serial.print(DisplayWords);
  
  } else {
      
      Serial.print(DisplayWords);
  
  }

  delay(500); //wait for half a second, so it is easier to read
}
