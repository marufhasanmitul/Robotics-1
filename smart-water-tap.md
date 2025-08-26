# Smart Water TAP

```javascript



void setup() {
  Serial.begin(9600);
  pinMode(8, OUTPUT);
  pinMode(A1, INPUT);

}



void loop() {

  int irValue=analogRead(A1);
  Serial.println(irValue);

  if(irValue<=50){
    digitalWrite(8, HIGH);
  }else{
    digitalWrite(8, LOW);
  }

  




  

}



```
