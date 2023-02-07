# KidsBits ADXL345

R11ケーブルで簡単接続。分解能 13 ビット、測定範囲 ±16g の小型、低電力、3 軸加速度計です。３つの方向XYZの加速度がわかります。

Arduino スケッチー＞ライブラリをインクルードー＞ライブラリの管理からFaBoで検索しADXL３４５のライブラリをインストールします。


##Arduino

```c
/**
 @file accelerometer.ino
 @brief This is an Example for the FaBo 3AXIS I2C Brick.

   http://fabo.io/201.html

   Released under APACHE LICENSE, VERSION 2.0

   http://www.apache.org/licenses/

 @author FaBo<info@fabo.io>
*/

#include <Wire.h>
#include <FaBo3Axis_ADXL345.h>

FaBo3Axis fabo3axis;

void setup()
{
  Serial.begin(9600); // シリアルの開始デバック用

  Serial.println("Checking I2C device...");

  if(fabo3axis.searchDevice()){
    Serial.println("I am ADXL345");
  }
  Serial.println("Init...");
  fabo3axis.configuration();
  fabo3axis.powerOn();
}

void loop() {
  int x;
  int y;
  int z;

  fabo3axis.readXYZ(&x,&y,&z);

  Serial.print("x: ");
  Serial.print(x);
  Serial.print(", y: ");
  Serial.print(y);
  Serial.print(", z: ");
  Serial.println(z);

  delay(1000);
}


```

<br>
<br>
FaBoライブラリ
[FaBo-3Axis-ADXL345-Library](https://github.com/FaBoPlatform/FaBo-3Axis-ADXL345-Library
){:target="_blank"}
