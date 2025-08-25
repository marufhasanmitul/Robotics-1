# Kitchen safety automation

```javascript






long currentTime=0;
long previousTime=0;


void setup() {
  Serial.begin(9600);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(A1, INPUT);
}



void loop() {
  
  
  int gasLevel = analogRead(A1);

  Serial.println(gasLevel);

  

  if(gasLevel >= 500){

      currentTime=millis();

      if(currentTime-previousTime >=50 ){
          previousTime=currentTime;
          int pinState=digitalRead(2);
          digitalWrite(2, !pinState);
          digitalWrite(3, !pinState);
          digitalWrite(4, !pinState);
          digitalWrite(7, !pinState);
          digitalWrite(8, !pinState);
          digitalWrite(9, !pinState);
     


      }

    

  }else if(gasLevel >= 150){
      currentTime=millis();

      if(currentTime-previousTime >=500 ){
          previousTime=currentTime;
          int pinState=digitalRead(2);
          digitalWrite(2, !pinState);
          digitalWrite(3, !pinState);
          digitalWrite(4, !pinState);
          digitalWrite(7, !pinState);
          digitalWrite(8, !pinState);
          digitalWrite(9, !pinState);
      }



  }
  
  
  
  
  
  else{
   
          digitalWrite(2, 0);
          digitalWrite(3, 0);
          digitalWrite(4, 0);
          digitalWrite(7, 0);
          digitalWrite(8, 0);
          digitalWrite(9, 0);
  }



  

}








```
