# KidsBits AnalogTemp

R11ケーブルで簡単接続。サーミスタを使用して温度を測定します。サーミスタは温度によって抵抗値が変化し、サーミスタの特性によって変化量がかわり、その電位差を測ることによって温度が分かります。


##Arduino

```c
void setup()
{
   Serial.begin(115200);
}
void loop()
{
  double val=analogRead(A0);
  Serial.print(val);
  Serial.print(":");
  double voltage=(val/1023)*3.3;
  double regstor = (3.3-voltage)/voltage*4700;
  Serial.print("Temprature:");
  Serial.println( 1/(  log(regstor/10000) /3950 + 1/(25+273.15))-273.15);
  delay(500);
}
```

サーミスタのB定数は3950
