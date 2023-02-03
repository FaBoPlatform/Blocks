# KidsBits Sound

R11ケーブルで簡単接続。A0ポートに接続します。音の大きさを取得できます。


##Arduino

```cpp
#define SOUNDSENSOR A0

int sensorValue = 0;

void setup() {
  Serial.begin(115200);
}

void loop() {
  sensorValue = analogRead(SOUNDSENSOR);
  Serial.println(sensorValue);
  delay(1);
}

```

シリアルプロッタにて確かめます。
環境に合わせて可変抵抗RP1で増幅レベルを調整します。
