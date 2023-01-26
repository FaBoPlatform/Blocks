# KidsBits ADXL345

R11ケーブルで簡単接続。分解能 13 ビット、測定範囲 ±16g の小型、低電力、3 軸加速度計です。３つの方向XYZの加速度がわかります。

Arduino スケッチー＞ライブラリをインクルードー＞ライブラリの管理からFaBoで検索しADXL３４５のライブラリをインストールします。


##Arduino

```c
#include <Wire.h>
#include <FaBo3Axis_ADXL345.h>

FaBo3Axis fabo3axis;

void setup()
{
  Serial.begin(115200); // シリアルの開始デバック用

  Serial.println("Checking I2C device...");

  if(fabo3axis.searchDevice()){
    Serial.println("I am ADXL345");
  }
  Serial.println("Init...");
  fabo3axis.configuration();
  fabo3axis.powerOn();
}

```

<br>
<br>
FaBoライブラリ
[FaBo-3Axis-ADXL345-Library](https://github.com/FaBoPlatform/FaBo-3Axis-ADXL345-Library
){:target="_blank"}
