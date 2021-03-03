---
title: Elasticsearch, Kibanaの勉強用メモ
date: 2020-12-30
tags: ELK
---

(自分用メモ, 随時更新)

## 残件

* Logstatshはまたそのうち

## 1. サンプルを動かす
* こちらを参考に以下をやった
   * https://qiita.com/kiyokiyo_kzsby/items/344fb2e9aead158a5545
* Dockerfileなど
    * https://github.com/ki4070ma/elasticsearch-kibana-sample

1. DockerでElasticsearch, Kibanaを構築
2. `curl` を使用してElasticsearchに対していろいろリクエストを送る
    * ローカルにあるサンプルデータ(.json)をElasticsearchへ登録
3. Kibanaで↑で登録したサンプルデータを使ってbalanceに関してPie chartを作成

## 2. Elasticsearchメモ
1. (Tips) 手元でcurlでelasticsearchに対してrequestを送って, jsonを見やすくするためには `jq` を使うと良いかも
   * (参考) https://qiita.com/takeshinoda@github/items/2dec7a72930ec1f658af
2. (Note) ローカルにあるサンプルデータ(.json)をアップロードするとき
  * account.json内にあるようにindexが必要そう
  * [link](https://qiita.com/kiyokiyo_kzsby/items/344fb2e9aead158a5545#%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%8A%95%E5%85%A5)
3. サンプルデータ

## 3. Kibanaメモ
1. Pie chartの作成
   * こちらでできた
      * https://dev.classmethod.jp/articles/amazon-elasticsearch-service-kibana6-tutorial-02/
2. Kibanaからデータの登録
   * Machine learning -> DnD
      * きれいなデータになっていればよさそう. filed名もこのときに決められる
   * https://www.elastic.co/jp/blog/importing-csv-and-log-data-into-elasticsearch-with-file-data-visualizer
3. 確認するリンク
   * https://thinkit.co.jp/article/14128

### 作りたいチャート
1. 日付毎の特定の値のカウント(A, B, C)
2. 日付毎のログから特定の値のカウント

## 4. Elasticsearchに入れるデータ
1. TBU

## 5. Elasticsearchにデータ入れたり
https://github.com/elastic/elasticsearch-py を使用すると吉

ref: https://qiita.com/atsushi0521/items/1d6342ef553babded8c5