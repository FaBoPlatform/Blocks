# KidsBits Photocel

R11ケーブルで簡単接続。A0ポートに接続します。センサーにかかる光の強さを測定します。

供給電圧は３.３Vにします。

##Arduino

```c
#define lightPin A0

int lightValue = 0;

void setup() {
  pinMode(lightPin,INPUT);
  Serial.begin(115200);
}

void loop() {
  lightValue = analogRead(lightPin);
  Serial.println(lightValue);
  delay(100);
}

```
