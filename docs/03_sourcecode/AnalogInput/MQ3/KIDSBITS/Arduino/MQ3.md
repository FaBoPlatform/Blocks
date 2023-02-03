# KidsBits MQ-3 Alchol

R11ケーブルで簡単接続。A1ポートに接続します。アルコールを検出します。
※高濃度のアルコールは揮発性が高く引火性がありますのでご注意ください。


##Arduino

```cpp
#define MQ3SENSOR A1

int sensorValue = 0;

void setup() {
  Serial.begin(115200);
}

void loop() {
  sensorValue = analogRead(MQ3SENSOR);
  Serial.println(sensorValue);
  delay(300);
}

```
