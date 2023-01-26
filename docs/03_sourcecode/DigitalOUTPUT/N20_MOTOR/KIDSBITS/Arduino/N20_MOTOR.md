# KidsBits N20＿MOTOR

R11ケーブルで簡単接続。

##Arduino

```c
#define PINIA 3
#define PINIB 2

void setup() {
  pinMode(PINIA,OUTPUT);
  pinMode(PINIB,OUTPUT);
}

void loop() {
  //反時計回り
  digitalWrite(PINIA,LOW);
  digitalWrite(PINIB,HIGH);
  delay(3000);
  //停止
  digitalWrite(PINIA,LOW);
  digitalWrite(PINIB,LOW);
  delay(2000);
  //時計周り
  digitalWrite(PINIA,HIGH);
  digitalWrite(PINIB,LOW);
  delay(3000);
  //停止
  digitalWrite(PINIA,LOW);
  digitalWrite(PINIB,LOW);
  delay(2000);
}


```
