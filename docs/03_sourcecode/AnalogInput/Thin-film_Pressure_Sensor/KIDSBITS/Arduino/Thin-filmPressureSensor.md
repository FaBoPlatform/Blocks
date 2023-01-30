# KidsBits Thin-film Pressure Sensor

R11ケーブルで簡単接続。A0ポートに接続します。センサーにかかる圧力を測定します。

供給電圧は３.３Vにします。

##Arduino

```c
#define analogPin A0

int value;

void setup() {
  Serial.begin(15200);
}

void loop() {
  int value = analogRead(analogPin);
  Serial.println(value);

}

```
