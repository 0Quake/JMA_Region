# 地震情報で用いる震央地名 ポリゴンデータ
気象庁の「地震情報で用いる震央地名」をまとめたGISデータです。地震火山関連コード表のAreaEpicenterと対応します。
GeoJSON形式で、各震央地名が指す地域をポリゴンとして表現しています。また、各ポリゴンのプロパティに震央地名とコードを設定しています。

### サンプル
[<img src="https://github.com/user-attachments/assets/6abe69f6-0844-4b62-8349-ae92860ce168" width="400px"><img src="https://github.com/user-attachments/assets/38699bf3-801c-4fad-94cd-2a60a432b5f2" width="400px">
](https://github.com/0Quake/JMA_Region/blob/main/%E9%9C%87%E5%A4%AE%E5%9C%B0%E5%90%8D.geojson)

[動的プレビュー](https://github.com/0Quake/JMA_Region/blob/main/%E9%9C%87%E5%A4%AE%E5%9C%B0%E5%90%8D.geojson)

## データの説明
|プロパティ|説明|例|
|-|-|-|
|properties.name|震央地名(AreaEpicenter)|東京都２３区|
|properties.id|コード|350|

本初子午線をまたぐ「ヨーロッパ西部」「地中海」「アフリカ西部」「南太平洋」のポリゴンは、本初子午線で分割し、マルチポリゴンで表現しています。また、飛び地のある「檜山地方」は、計2つのポリゴンをマルチポリゴンで表現しています。

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
