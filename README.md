# Ultra96V2用マルチI/O拡張カード

まだ手元に届いていないので動くかどうかわかりませんが...

## 開発イメージ
 ![開発イメージ](documents/develop_image.png "開発イメージ")

## 機能

こんな感じの [Ultra96V2](https://www.avnet.com/wps/portal/japan/products/product-highlights/ultra96/) むけ多機能ボード。

コンセプトは

- [FusionPCB](https://www.fusionpcb.jp)さんの$4.9基板で作る
- [ZYBO](https://reference.digilentinc.com/reference/programmable-logic/zybo-z7/start) の良さ(PLのI/O機能の充実)の追加
- [Raspberry PI](https://ja.wikipedia.org/wiki/Raspberry_Pi) の良さ(PSのI/O機能の充実)の追加

です。

主な機能として

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

ですが、まだ基板が届いていないのでこのうちいくつ動くやら...

特に MIPI-CSI は、一次試作ではあとちょっとのところで2チャンネルともクロック含めた3レーンのうち1レーンだけ通らない状態でリベンジ中です(厳密なインピーダンスコントロールを依頼していませんので、[こちら](http://nahitafu.cocolog-nifty.com/nahitafu/2008/11/post-57a1.html)を参考にさせて頂いて、設計時の机上計算のみ行っています)。


## 回路図

回路図は[こちら](documents/ultra96v2_multi_io_schematic.pdf)
