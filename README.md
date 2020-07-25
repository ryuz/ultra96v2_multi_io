# Ultra96V2用マルチI/O拡張カード

現在デバッグ中ですが、MIPI-CSI の片方は動作確認できました。

## 開発イメージ
 ![開発イメージ](documents/develop_image.png "開発イメージ")

## 機能

こんな感じの [Ultra96V2](https://www.avnet.com/wps/portal/japan/products/product-highlights/ultra96/) むけ多機能ボード。

コンセプトは

- [FusionPCB](https://www.fusionpcb.jp)さんの$4.9基板で作る
- [ZYBO](https://reference.digilentinc.com/reference/programmable-logic/zybo-z7/start) の良さ(PLのI/O機能の充実)の追加
- [Raspberry PI](https://ja.wikipedia.org/wiki/Raspberry_Pi) の良さ(PSのI/O機能の充実)の追加
- 使いたい機能だけ部品実装すれば最低限のコストで使える

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


特に MIPI-CSI は、[こちら](http://nahitafu.cocolog-nifty.com/nahitafu/2008/11/post-57a1.html)を参考にさせて頂いて、基板厚 0.6mm の想定で設計時の机上計算のみ行っています)。


## 回路図

回路図は[こちら](documents/ultra96v2_multi_io_schematic.pdf)


## 修正履歴

- Rev.1 2020/02/11
   - 修正内容
       - 初版
   - 動作状況
       - MIPI-CSI が同パターンの別基板でデータ受信でき無かったため、部品温存で試さずに Rev.2 製造へ

- Rev.2 2020/03/08
   - 修正内容
       - MIPI 配線レイアウト変更
       - 基板厚を 0.6mm に変更して発注
   - 動作状況
       - J3のMIPI-CSI動作開始(I2Cプルアップをリワーク修正)
       - PMODの出力パルス波形確認
       - 他はこれから試す予定

- Rev.3 作業中
   - MIPI-CSI用 I2C プルアップ抵抗抜け修正(R23～26追加)
   - LS_GPIO_2 と LS_GPIO_6 の U4 への接続をスワップ
