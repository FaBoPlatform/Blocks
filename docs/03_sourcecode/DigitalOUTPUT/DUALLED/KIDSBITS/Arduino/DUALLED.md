# KidsBits Dual LED

R11ケーブルで簡単接続。Dual LEDは１つのLEDから緑色と赤色が発光できます。

GP２は赤、GP３を緑色に接続し、交互点灯させます。

##Arduino

```cpp
#define GREENPIN 2
#define REDPIN 3


void setup() {
  pinMode(GREENPIN, OUTPUT);
  pinMode(REDPIN, OUTPUT);
}

void loop() {
  digitalWrite(GREENPIN, HIGH);
  digitalWrite(REDPIN, LOW);
  delay(1000);
  digitalWrite(GREENPIN, LOW);
  digitalWrite(REDPIN, HIGH);
  delay(1000);
}

```
