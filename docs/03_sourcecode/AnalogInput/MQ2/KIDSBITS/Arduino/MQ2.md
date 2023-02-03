# KidsBits MQ-2 Gas

R11ケーブルで簡単接続。A1ポートに接続します。ガス漏れ検知器向けのセンサーです。プロパンガスや煙に対して高い感度を持ち、
天然ガス、その他の可燃性蒸気をよく検出します。
※プロパンガスやLNGなどの可燃性ガスは爆発、引火し大変危険です。可燃性ガスでは実験は絶対しないでください。

##Arduino

```cpp
#define MQ2SENSOR A1

int sensorValue = 0;

void setup() {
  Serial.begin(115200);
}

void loop() {
  sensorValue = analogRead(MQ2SENSOR);
  Serial.println(sensorValue);
  delay(300);
}

```
