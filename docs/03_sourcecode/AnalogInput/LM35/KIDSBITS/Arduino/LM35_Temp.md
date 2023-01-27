# KidsBits LM35 Temp

R11ケーブルで簡単接続。LM35は出力電圧が温度と正比例します。

##Arduino

```c
#define ANALOGPIN A0

void setup(){
  Serial.begin(115200);
}

void loop(){
  int i = analogRead(ANALOGPIN);
  float temprature = ((3.3 * i) / 1024) * 100;
  Serial.println(temprature);
  delay(1000);

}
```
