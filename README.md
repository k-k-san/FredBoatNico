# FredBoatNico

ニコニコ動画対応版FredBoatのdockerイメージを作成します。

## build方法
dockerとdocker-composeの使える環境で、
```sudo docker-compose build```
を実行すればビルドされます。

## 使用方法
ほぼオリジナルのFredBoatです。<br>
従って使用方法等は公式のマニュアルをご覧ください。

## ニコニコ動画の動画を再生する際
ニコニコの動画を再生する際も同様に```{prefix}play URL```が使用できます。<br>
対応しているURL形式は以下です。<br>
```http://```または```https://```または無し<br>
続けて、<br>
```www.```または```sp.```または無し<br>
続けて<br>
```nicovideo.jp/watch/```または```nico.ms/```<br>
続けて<br>
```sm[0-9]```または```so[0-9]```または```[0-9}```<br>
となっています。<br>
ソースコード内では<br>
`^(?:http://|https://|)(?:www\\.|sp\\.|)(?:nicovideo\\.jp/watch/|nico\\.ms/)((?:sm|so|)[0-9]+)(?:\\?.*|)$`<br>
となっています。<br>

## 注意
けーさんは自信がないのでpull requestを送る気は今のところありません。<br>
本家が更新されてもこちらが更新されるのは私が気が向いた時です。<br>
また、これを使って何かあっても知りません。自己責任でお願いします。<br>
