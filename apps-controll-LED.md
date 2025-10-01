# Use Module
- HC 06
- Arduino

 # Connection
 
<img width="299" height="278" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/b97fbb19-a772-4dae-9eef-4b752872a859" />


![HC](https://github.com/user-attachments/assets/44d30087-d9bb-47b9-9dcb-df8e8dfb56bb)

```javascript


String text="";
void setup() {
  Serial.begin(9600);
  pinMode(8,OUTPUT);

 

}



void loop() {

 
  if( Serial.available() ){
     text=Serial.readStringUntil("\n");
     text.trim();
     Serial.println(text);

     if(text.equalsIgnoreCase("on")){
         digitalWrite(8,HIGH);
     }
     else if(text.equalsIgnoreCase("off")){
         digitalWrite(8,LOW);
     }


     

     delay(100);
  }

  

  
}

```
