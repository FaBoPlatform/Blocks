# USB Serial

シリアル通信は、一対一で主にマイコンどおしの通信に使われます。あらかじめ通信速度を決めてから通信を行います。

##Arduino

##USBを使ったシリアル通信

Raspberry pi picoへ送信した文字を受信するエコーバックを確認します。

```c
void setup()  
{
  Serial.begin(115200);
  while (!Serial) {
    ;
  }
  Serial.println("Goodnight moon!");
}

void loop()
{
  if (Serial.available()){
    char c = Serial.read();
    Serial.println(c);
  }
}
```

書き込みが完了後、シリアルモニタを開いて通信速度を115200bpsに設定し、改行なしにします。任意の文字を入力し、送信ボタンを押します。

入力後、送信された文字が１バイトづつ受信され表示されます。

確認後は、シリアルモニタを閉じます。

##FaBo USB Serialを使ったシリアル通信

次は、UARTピン１にUSB Serialモジュールを刺します。

```c
void setup()  
{
  Serial1.begin(115200);
  while (!Serial1) {
    ;
  }
  Serial1.println("Goodnight moon!");
}

void loop()
{
  if (Serial1.available()){
    char c = Serial1.read();
    Serial1.println(c);
  }
}
```

次は、UART２にUSB Seria2モジュールを刺します。

```c
void setup()  
{
  Serial2.begin(115200);
  while (!Serial2) {
    ;
  }
  Serial2.println("Goodnight moon!");
}

void loop()
{
  if (Serial2.available()){
    char c = Serial2.read();
    Serial2.println(c);
  }
}
```
