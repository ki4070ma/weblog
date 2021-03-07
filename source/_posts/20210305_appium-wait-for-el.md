---
title: Appiumで特定のelementが表示されるまで待つ
date: 2021-03-05
tags: [Appium, Python, Technology]
---

<!-- toc -->

# 必要な背景

以下のようなケースで役に立ちます

* (特にAndroid) 端末の動作が遅い時などに画面遷移で時間がかかるとき
* ネットワークの状態によって待ちが発生するとき

Azure pipeline上のAndroid emulatorでAppiumを動作させるときに活躍しました

# Sample code

以前自身で作成したコードです (contribution)
https://github.com/appium/python-client/blob/master/test/functional/test_helper.py

{% ghcode https://github.com/appium/python-client/blob/66208fdbbc8f0a8b0e90376b404135b57e797fa5/test/functional/test_helper.py 81 97 %}

上記の `wait_for_element` が定義されている状態で, 以下のコードで動作します


```python
# 'Bouncing Balls' というテキストを持つelementを 10 秒のタイムアウトで待つ処理. 返り値は検出したelement.
el = wait_for_element(self.driver, MobileBy.ACCESSIBILITY_ID, 'Bouncing Balls')
```