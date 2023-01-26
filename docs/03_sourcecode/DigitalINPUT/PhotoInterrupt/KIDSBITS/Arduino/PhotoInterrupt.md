# KidsBits PhotoInterrupt

R11ケーブルで簡単接続。主に回転を検出します。割り込みを使う場合は、割り込み先の変数にvolatileを付けます。

##Arduino

```c
int summary = 0;
volatile int rotation_Count = 0;

void setup() {
  attachInterrupt(2,Counter,RISING);
  Serial.begin(115200);
}

void loop() {
  if (summary != rotation_Count){
    Serial.print(rotation_Count);
    Serial.println("rotation count");
    summary = rotation_Count;   
  }
  delay(100);
}
  void Counter(){
    rotation_Count++;
    }

```
