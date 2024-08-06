# 地震情報で用いる震央地名 ポリゴンデータ
気象庁の「地震情報で用いる震央地名」をまとめたGISデータです。GeoJSON形式で、各震央地名が指す地域をポリゴンとして表現しています。また、各ポリゴンのproperties.nameに震央地名を「東京都２３区」のような形式で設定しています。

### サンプル
<img src="https://github.com/user-attachments/assets/6abe69f6-0844-4b62-8349-ae92860ce168" width="400px">

## 出典
気象庁ホームページ
- [地震情報で用いる震央地名](https://www.data.jma.go.jp/eqev/data/joho/region/index.html)
- [別紙３ 震央地名地図](https://www.jma.go.jp/jma/press/0609/20b/20060920bessi3.pdf)

上記出典には、政府標準利用規約 第2.0版（[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode.ja)互換）が適用されます。

## ライセンス
パブリックドメインとします。ご自由にお使いください。  
This work by Benidate is marked with CC0 1.0 Universal

## 作成方法
1. 「別紙３ 震央地名地図」の1ページを高画素数のpng画像に変換
2. 上記画像をQGISに読み込み、ジオリファレンス（位置合わせ）を行う
3. QGISでグリッドを生成（緯経度0.1度間隔、緯経度それぞれ0.05度ずらす）
4. グリッドを頼りに根性で手書き（スナップ機能を使用し正確に描画）

## お願い
データに謝り等あればissueでお知らせください。
