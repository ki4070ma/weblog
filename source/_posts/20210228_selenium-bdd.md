---
title: Selenium で BDD
date: 2021-02-28
tags: [selenium, BDD, python, Technology]
---

<!-- toc -->

## BDD とは

[ビヘイビア駆動開発(Behavior Driven Development; BDD)](https://ja.wikipedia.org/wiki/%E3%83%93%E3%83%98%E3%82%A4%E3%83%93%E3%82%A2%E9%A7%86%E5%8B%95%E9%96%8B%E7%99%BA) より

`ビヘイビア駆動開発とは、プログラム開発手法の一種で、テスト駆動開発から派生した物である`

## Gherkin

BDD記法としては, Gherkin (ガーキン) というものに沿っており, 以下の3つから成っています

* Given (前提 -> 状態を記述)
* When (もし -> 振舞いを記述)
* Then (ならば -> 振舞いの結果を記述)

参考
https://cucumber.io/docs/gherkin/languages/
https://cucumber.io/docs/gherkin/reference/

```
Describe an initial context (Given steps)
Describe an event (When steps)
Describe an expected outcome (Then steps)
```

## 各言語での BDD フレームワーク

実際に各プログラミング言語で BDD フレームワークが存在します
(上記 wikipedia より一部抜粋)

各フレームワークと selenium, appium などを組み合わせて使用することが一般的かと思います

* Ruby
   * RSpec
* Java
   * JBehave
   * Instinct
   * JDave
   * beanSpec
   * Tumbler
* .Net
   * NSpec
   * Specter
*  Groovy
   * GSpec
   * easyb
* Python
   * PySpec
   * behave

## Python での BDD フレームワーク

2年前の記事ですが, Python の BDD のフレームワークの比較です
https://automationpanda.com/2019/04/02/python-bdd-framework-comparison/

以下の 5 つが紹介されていました
(star は 2021/03 時点)

* behave (2275 stars, https://github.com/behave/behave )
* pytest-bdd (780 stars, https://github.com/pytest-dev/pytest-bdd )
* radish ( 153 stars, https://github.com/radish-bdd/radish )
* lettuce ( 1228 stars, https://github.com/gabrielfalcao/lettuce)
* freshen ( 365 starts, https://github.com/rlisagor/freshen )
   * メンテされていない

star の数とメンテされているかどうかからも `behave` がよさそうです
上記サイトでは `pytest-bdd` が推奨されていました, こちらもメンテナされているようです

詳細確認できていませんが, gauge もよさそうです
Thoughtworks が作成しており, 開発も活発のようです
Python以外の言語でも使用できます

https://gauge.org/
https://github.com/getgauge/gauge

## [Python] Selenium + BDD フレームワークのサンプルコード

こちらに slenium + BDD(behave) のサンプルコードを置いています

https://github.com/ki4070ma/selenium-bdd-sample
