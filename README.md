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
|properties.id|コード|350|
|properties.name|震央地名(日本語)|東京都２３区|
|properties.name_kana|震央地名(ひらがな)|とうきょうとにじゅうさんく|
|properties.name_en|震央地名(英語)|23 wards, Tokyo|
|properties.name_zh-cn|震央地名(中国語_簡体字)|东京都23区|
|properties.name_zh-tw|震央地名(中国語_繁体字)|東京都２３區|
|properties.name_ko|震央地名(韓国語)|도쿄도 23구|
|properties.name_pt|震央地名(ポルトガル語)|23 distritos da Região Metropolitana de Tóquio|
|properties.name_es|震央地名(スペイン語)|23 districtos de Metrópoli de Tokio|
|properties.name_id|震央地名(インドネシア語)|23 Distrik Ibu Kota Tokyo|
|properties.name_vi|震央地名(ベトナム語)|23 quận thủ đô Tokyo|
|properties.name_tl|震央地名(タガログ語)|23 Wards ng Tokyo Metropolis |
|properties.name_th|震央地名(タイ語)|23 แขวงของมหานครโตเกียว|
|properties.name_ne|震央地名(ネパール語)|टोक्यो महानगरपालिकाको २३ सहरहरू|
|properties.name_km|震央地名(クメール語)|តូក្យូ​ 23 សង្កាត់|
|properties.name_my|震央地名(ビルマ語)|23ရပ်ကွက်၊ တိုကျို|
|properties.name_mn|震央地名(モンゴル語)|Токио нийслэл, 23 хороо|


- 本初子午線をまたぐ「ヨーロッパ西部」「地中海」「アフリカ西部」「南太平洋」のポリゴンは、本初子午線で分割し、マルチポリゴンで表現しています。
- 飛び地のある「檜山地方」は、計2つのポリゴンをマルチポリゴンで表現しています。

## 出典
気象庁ホームページ
- [地震情報で用いる震央地名](https://www.data.jma.go.jp/eqev/data/joho/region/index.html)（使用部分：震央地名の境界線）
- [別紙３ 震央地名地図](https://www.jma.go.jp/jma/press/0609/20b/20060920bessi3.pdf)（使用部分：震央地名の境界線）
- [個別コード表](https://xml.kishou.go.jp/tec_material.html)（使用部分：日本語地名）
- [予報区等GISデータ「地震情報／細分区域」](https://www.data.jma.go.jp/developer/gis.html)（使用部分：一部のひらがな地名）
- [多言語辞書データ](https://www.data.jma.go.jp/developer/multilingual.html)（使用部分：多国語地名）

上記出典には、政府標準利用規約 第2.0版（[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode.ja)互換）が適用されます。

## ライセンス
パブリックドメインとします。ご自由にお使いください。  
This work by Benidate is marked with CC0 1.0 Universal

## 作成方法
1. 「別紙３ 震央地名地図」の1ページを高画素数のpng画像に変換
2. 上記画像をQGISに読み込み、ジオリファレンス（位置合わせ）を行う
3. QGISでグリッドを生成（緯経度0.1度間隔、緯経度それぞれ0.05度ずらす）
4. グリッドを頼りに根性で手書き（スナップ機能を使用し正確に描画）
5. コード表を参照してコードから日本語震央地名を割り出し、登録
6. 多言語辞書データを参照してコードから多国語地名を割り出し、登録
7. 一致する地名が「地震情報／細分区域」に存在する場合、細分区域GISデータに併記されているひらがな地名を採用
8. それ以外の場合、手動でひらがな地名を作成

## お願い
データに誤り等あればissueでお知らせください。
