# Automatic Street Light

```javascript

void setup() {
  Serial.begin(9600);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(A1, INPUT);
}

// Threshold টিউন করতে হবে Serial Monitor দেখে
const int darkThreshold   = 300;  // এর নিচে = অন্ধকার => লাইট ON
const int brightThreshold = 400;  // এর উপরে = যথেষ্ট আলো => লাইট OFF

bool lightOn = false;  // লাইটের স্টেট সংরক্ষণ

void loop() {
  int ldrValue = analogRead(A1);
  Serial.println(ldrValue);
  delay(500);

  if (!lightOn && ldrValue <= darkThreshold) {
    // অন্ধকার => লাইট চালু
    lightOn = true;
    digitalWrite(2, HIGH);
    digitalWrite(3, HIGH);
    digitalWrite(4, HIGH);
    Serial.println("Lights ON");
  } 
  else if (lightOn && ldrValue >= brightThreshold) {
    // আলো => লাইট বন্ধ
    lightOn = false;
    digitalWrite(2, LOW);
    digitalWrite(3, LOW);
    digitalWrite(4, LOW);
    Serial.println("Lights OFF");
  }
}

```
