# Ultra96V2用マルチI/O拡張カード

まだ手元に届いていないので動くかどうかわかりませんが...

## 開発イメージ
 ![開発イメージ](documents/develop_image.png "開発イメージ")

## 機能

こんな感じの多機能ボード。

コンセプトは [Ultra96V2](https://www.avnet.com/wps/portal/japan/products/product-highlights/ultra96/) に [ZYBO](https://reference.digilentinc.com/reference/programmable-logic/zybo-z7/start) の良さ(PLのI/O機能の充実)と、[Raspberry PI](https://ja.wikipedia.org/wiki/Raspberry_Pi) の良さ(PSのI/O機能の充実)を追加すること。


- PLの機能
    - TXS0108で3.3V双方向変換した12pin PMOD × 2個
    - RaspberryPI互換 MIPI-CSIコネクタ× 2個
    - LED × 4個
    - プッシュスイッチ × 2個 
    - ディップスイッチ(4bit) × 1個 
    - 25MHzクロック供給
- PSの機能
    - LED × 2個
    - TXS0108で3.3V双方向変換したGPIO
    - TXS0108で3.3V双方向変換したI2C
    - TXS0108で3.3V双方向変換したSPI
- その他の機能
    - 隠れると困るPWR/RSTスイッチの引き出し
    - 申し訳程度にUSB2.0信号を引き出したピンヘッダ

## 回路図

回路図は[こちら](documents/ultra96v2_multi_io_schematic.pdf)
