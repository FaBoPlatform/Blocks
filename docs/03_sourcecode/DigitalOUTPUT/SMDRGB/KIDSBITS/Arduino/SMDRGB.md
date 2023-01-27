# KidsBits SMD RGB

R11ケーブルで簡単接続。赤色、緑色、青色のLEDが1個にまとまったLEDを制御します。
それぞれ色のピンをローの状態にするとLEDが発光します。ハイの状態は、LEDが消灯します。

##Arduino

RGBをそれぞれ１秒ごとに赤、緑、青の順番に発光させます。

```cpp
#define REDLED    2
#define GREENLED  3
#define BLUELED   20

void setup() {
  pinMode(REDLED, OUTPUT);
  pinMode(GREENLED, OUTPUT);
  pinMode(BLUELED, OUTPUT);
  digitalWrite(REDLED, HIGH);
  digitalWrite(GREENLED,HIGH);
  digitalWrite(BLUELED,HIGH);
}

void loop() {
  digitalWrite(REDLED,LOW);
  delay(1000);
  digitalWrite(REDLED,HIGH);
  digitalWrite(GREENLED,LOW);
  delay(1000);
  digitalWrite(GREENLED,HIGH);
  digitalWrite(BLUELED,LOW);
  delay(1000);
  digitalWrite(BLUELED,HIGH);
}

```
