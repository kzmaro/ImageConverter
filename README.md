# ImageConverter

## 〜Summary〜
Pythonの画像処理の入門として作ったもの。   
入力した画像(PNG,JPG)を[GBstudio](https://www.gbstudio.dev/)で扱える4色の色に変換するアプリケーション。

## 〜Requrirements〜
```
Python 3.7
Pillow (6.0.0)
```
## 〜Usage〜
.pyファイルを実行します。4つの質問に答えることで目的の画像を出力することができます。  

1. まず、グレースケールに変換を行ってからそれを元にして画像を4つの値に分けます。  
    5種類のグレースケール変換方法から選んで数字を入力してください。選べるのはNTSC係数による加重平均法、   
    中間値法、単純平均化法、Gチャンネル法、HDTV係数による加重平均と補正法 の5種類です。   

2. 画像のパスをフルパスで入力してください。   
## 注意！！　警告にも出ますが、パスには拡張子を含めないでください！

3.  入力ファイルがPNGかJPGファイルかをp/jで選択します。

4.  モードを選択します。GBStudio用の緑系画像なら1,普通のグレースケールなら2を選択します。

5. ファイルが出力されます

以下の画像は左上から右にNTSC,中間値、平均化、Gチャンネル、HDTV、元画像です。
![img](https://github.com/kzmaro/ImageConverter/blob/images/girl.png)
![img](https://github.com/kzmaro/ImageConverter/blob/images/sakura.png)

## GBstudioへの適用方法
適するサイズの画像を用意して変換しても上の右の図のように正しく表示されません。（この画像コワイ、、、）   
これはメモリリークしてるからだと思われます。GBstudioは実機でのプレイができるようになっているため、メモリなども実機の容量を再現してるからでしょう。   
この問題を解決するためには画像をあらくすればいいです。
[ドット絵コンバータ](https://app.monopro.org/pixel/)さんで前処理、（ドットの大きさは3以上が望ましい）を行うことできちんと表示できました！   
画像中左が処理を施したもの。その右が実際にゲーム画面で表示されている様子。   

また、マップチップの場合でも同様の処理を行います。   
マップチップの場合チップに前処理を行ってからImageProcess.pyを実行し、そして変換した画像で、編集ツールを用いてマップを作るという順番を推奨します。   
(マップを作ってからImageProcess.pyの処理を実行すると使用ソフトによって正しく処理が行えなかったりGB側でCLエラーが発生するため)   
マップチップ左上は元画像、その下は前処理（ドット3）を施したもの、右は実際にゲーム画面で背景画像として利用してキャラクターを動かしてみたものです。   

![img](https://github.com/kzmaro/ImageConverter/blob/images/GBapply.png)

## 今後の改良予定
- 緑系4色だけでなく普通のグレースケールにも対応。2019.05.03対応済
- PNG or JPG　出力を、入力した拡張子によらず選べるように設定


画像は全てフリーのものを使用させてもらっています。
