# KidsBits RELAY

R11ケーブルで簡単接続。リレーはマイコンのみでは制御できない交流電源、高い電圧や大電流のスイッチングを実現します。

##Arduino

RGBをそれぞれ１秒ごとに赤、緑、青の順番に発光させます。

```cpp
#define RERAYPIN    2

void setup() {
  pinMode(RERAYPIN, OUTPUT);
}

void loop() {
  digitalWrite(RERAYPIN,LOW);
  delay(1000);
  digitalWrite(RERAYPIN,HIGH);
  delay(1000);
}

```
