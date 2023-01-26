# KidsBits SidePort

R11ケーブルで簡単接続。

##Arduino

```c
int ota;
int otb;

void setup() {
  Serial.begin(115200);
}

void loop() {
  ota = analogRead(A0);
  otb = analogRead(A1);
  Serial.print("A0:");
  Serial.print(ota);
  Serial.print(",A1:");
  Serial.println(otb);
  delay(100);
}
```
