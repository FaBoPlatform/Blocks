# FaBo Blocks LED

##Arduino

###Raspbery pi picoのピンアサイン（Arduino）


DigitalピンにLEDモジュールを刺します。

１秒ごとにGP３に繋いだLEDを点滅させます。

setup関数を一度しか実行されない関数(初期設定)で、loop関数（メイン動作）は繰り返します。


```c
void setup() {
  pinMode(3, OUTPUT);
}

void loop() {
  digitalWrite(3, HIGH);
  delay(1000);                     
  digitalWrite(3, LOW);
  delay(1000);
}
```
