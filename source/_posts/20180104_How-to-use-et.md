---
title: 探索的テストの使い方
date: 2018-01-04
tags: [SoftwareTest, ExploratoryTest]
---

 # 探索的テストとは

```
探索的テストは、テストの目的が含まれたテストチャータを基にしたもので、
テスト設計、テスト実行、テスト記録や学習を並行して同じ時間枠内で実行する。
このアプローチは、仕様がほとんどなかったり、不十分であったり、
スケジュール的な余裕がない場合や、他の形式的なテスト技法を補完する場合に効果が大きい。
探索的テストは、テストプロセスのチェックや、きわめて重大な欠陥を見つけ出すのに役に立つ。 
```

* http://jstqb.jp/dl/JSTQB-Syllabus.Foundation_Version2011.J01.pdf
* 探索的テストについては調べるといろいろ出てくる

# 探索的テストの使い方
1. チーム内の他のメンバーが作った機能の理解
    * 自分が作っていない機能を探索的にテストすることでその機能への理解が深まる
    * みんなが集まってテストできれば, 不明点(仕様やロジックなど)を作成者にすぐ聞くことができ, それを他のメンバーも聞くことができるので暗黙知や知識の共有にもなる
1. 品質の確認
    * [Session-based testing](https://en.wikipedia.org/wiki/Session-based_testing)などを使えば品質を確認, レポートすることができる
    * (参考) [「探索的テスト」を活用して品質を高める](http://www.nttdata.com/jp/ja/insights/trend_keyword/2014072401.html)
1. バグ出し
    * テストスクリプトなどの用意をせず, どのあたりをテストするのかをざっくり方針決めてテストするだけである程度の致命的なバグを見つけることができるため費用対効果(ROI)は高い
        * バグを仕込んで直すまでの時間が短ければ短いほど修正コストは低いので, 機能がある程度出来たら行うと良い
        * 開発チームで行うとよりよい
1. 回帰テスト
    * https://techblog.king.com/moving-from-scripted-regression-testing-to-exploratory-testing/
1. 上記の使い方を同時に複数行うこともできる

# 探索的テストはソフトウェアテストの1つのスタイル
* 「探索的テストってなんですか？」(高橋寿一さん)より
    * http://jasst.jp/symposium/jasst14kyushu/pdf/S3.pdf
* 探索的テストは特徴を把握して自分たちに合うように使うとよい

{% iframe https://rcm-fe.amazon-adsystem.com/e/cm?lt1=_blank&bc1=000000&IS2=1&bg1=FFFFFF&fc1=000000&lc1=0000FF&t=ki4070ma-22&language=ja_JP&o=9&p=8&l=as4&m=amazon&f=ifr&ref=as_ss_li_til&asins=4798130605&linkId=6829f54f78a9c756c81ff11a4a3f0a99 120 240 %}

{% iframe https://rcm-fe.amazon-adsystem.com/e/cm?lt1=_blank&bc1=000000&IS2=1&bg1=FFFFFF&fc1=000000&lc1=0000FF&t=ki4070ma-22&language=ja_JP&o=9&p=8&l=as4&m=amazon&f=ifr&ref=as_ss_li_til&asins=4798165034&linkId=bd12d315c013fc821f7b3503ce1ed22c 120 240 %}

ref: https://qiita.com/atsushi0521/items/e1ba80010ed34aca26bf