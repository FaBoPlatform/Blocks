# KidsBits RELAY

R11ケーブルで簡単接続。リレーはマイコンのみでは制御できない交流電源、高い電圧や大電流のスイッチングを実現します。
漏電や短絡をしないように配線してください。最悪けが、発火、火災、死亡の危険性があります。
４２V以上を扱う場合は、最悪感電または死亡の危険性があります。

##Arduino

リレーモジュールを２ピンに接続します。リレーのスイッチが3秒ごと開閉します。

```cpp
#define RERAYPIN    2

void setup() {
  pinMode(RERAYPIN, OUTPUT);
}

void loop() {
  digitalWrite(RERAYPIN,LOW);
  delay(3000);
  digitalWrite(RERAYPIN,HIGH);
  delay(3000);
}

```
