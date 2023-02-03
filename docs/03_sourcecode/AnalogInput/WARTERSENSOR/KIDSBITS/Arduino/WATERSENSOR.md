# KidsBits WaterSensor

R11ケーブルで簡単接続。A0ポートに接続します。基板の配列された端子の電位差より水位を計測します。


##Arduino

```cpp
#define WATERSENSOR A0

int sensorValue = 0;

void setup() {
  Serial.begin(115200);
}

void loop() {
  sensorValue = analogRead(WATERSENSOR);
  Serial.println(sensorValue);
  delay(1000);
}


```
