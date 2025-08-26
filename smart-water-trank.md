# Smart Water Trank


```javascript

long currentTime=0;
long previousTime=0;

void setup() {
  Serial.begin(9600);
  pinMode(12, OUTPUT);

  pinMode(A1, INPUT);

}



void loop() {

  int waterLevel=analogRead(A1);
  Serial.println(waterLevel);

  if(waterLevel>=400){
      digitalWrite(12,LOW);
      previousTime=millis();
  }else {
    currentTime=millis();
    if(currentTime-previousTime >=10000){
      digitalWrite(12,HIGH);
    }
  }





  

}










```
