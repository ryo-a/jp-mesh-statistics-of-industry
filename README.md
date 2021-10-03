# 工業統計メッシュデータ CSV版

経済産業省の「[工業統計メッシュ検索システム](https://www.meti.go.jp/statistics/tyo/kougyo/mesh/index.html)」にてPDF形式で公開されている、工業統計メッシュデータをCSV形式に直したデータです。3000以上のPDFファイルを1つのCSVに集計しました。

## ヘッダ

### mesh_1km.csv

1km メッシュ単位の情報。なお、1km単位での地名はデータがないため、ここでの地域メッシュ名は10km単位のものであることに留意。

- region_name_1_20000 : 20万分の1地勢図での地域名
- prefecture : 都道府県名
- region_name_10km : 10km四方のメッシュ（2次メッシュ）における地域メッシュ名
- mesh_10km : 10km四方のメッシュ（2次メッシュ）番号
- mesh_1km : 1km四方のメッシュ番号（先頭6桁は `mesh_10km` と同一）
- number_of_factories : 事業所数
- number_of_workers : 従業者数
- shipment : 製造品出荷額等（万円）

### mesh_10km.csv

上記 1km メッシュの情報を 10km メッシュ単位で集計したもの。

- region_name_1_20000 : 20万分の1地勢図での地域名
- prefecture : 都道府県名
- region_name_10km : 10km四方のメッシュ（2次メッシュ）における地域メッシュ名
- mesh_10km : 10km四方のメッシュ（2次メッシュ）番号
- number_of_factories : 事業所数
- number_of_workers : 従業者数
- shipmen : 製造品出荷額等（万円）


## 留意事項

取得したPDFに対して機械的な処理を実施したものです。

- 空欄のメッシュ、あるいはデータが存在しないメッシュの行は存在していません。データが掲載されているメッシュのみCSVに記載されています。
- `製造品出荷額等`における `X` は `0` として扱っています。

## 既知の問題

- 一部メッシュの地名・都道府県名が取得できていません (2021-10-03)
  - [環境庁のメッシュ-地名対応表](http://gis.biodic.go.jp/webgis/files/vgmap_dllist.pdf)をデータソースとして用いたことに起因します。環境省での調査が行われていない地域はこちらに記載されていません。
  - より適切かつmachine readableな地名・メッシュ対応データがあれば差し替えます