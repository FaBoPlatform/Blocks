# KidsBits 4-DigitDisplay

R11ケーブルで簡単接続。KidsBits７セグメントLEDドライバIC TM1637搭載で複雑な配線なしで７セグメントLEDを制御できます。

##Arduino

４桁の７セグメントLEDを数字０から９まで表示させます。
GPIO出力ピンを６ピン、CLOCKピンを７ピンに接続します。
FaBoTM1637のライブラリをダウンロードします。（準備中）


```cpp
#include "FaBoTM1637.h"
#define CLK 7  
#define DIO 6

int8_t Numbers[] = {0,1,2,3,4,5,6,7,8,9};
int8_t Digits[4];
unsigned char count = 0;

TM1637 FaBotm1637(CLK,DIO);

void setup()
{
  FaBotm1637.init();
  FaBotm1637.setDimming(7);
}
void loop()
{   
    FaBotm1637.showDot(ON);
    for(unsigned char NumberDigit = 0;NumberDigit < 4;NumberDigit ++){
      for (int i = 0;i<4;i++){
          FaBotm1637.showNumber(i,Numbers[count]);
      }
          count ++;
          if(count == sizeof(Numbers)) count = 0;
          delay(1000);
    }
}

```
