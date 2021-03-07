---
title: Appium による macOS の操作
date: 2021-02-26
tags: [Appium, macOS, Python]
---

## 準備

* macOS 10.15 以上
* Xcode 12 以上

がインストールされている状態で, `Xcode Helper app` のアクセシビリティアクセスが有効化されている必要があります
App自体は以下に存在しており, 

```
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/Library/Xcode/Agents/Xcode Helper.app
```

まず `/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/Library/Xcode/Agents/` を Finder で開いて, 
`Xcode Helper app` を ドラッグ&ドロップで `システム環境設定` の `Security & Privacy -> Privacy -> Accessibility` のリストへもっていきます
こちらは一度のみでよいです

これで準備完了です

## 実行

あとは appium が実行されていて, appium-python-client がインストールされている状態であれば, 以下のコードで macOS 上の TextEditor を動かすことができます
以下のコードを `script.py` として保存して, 実行は `pytest script.py` です

```python
import pytest

from appium import webdriver


@pytest.fixture()
def driver():
    drv = webdriver.Remote('http://localhost:4723/wd/hub', {
        # automationName capability presence is mandatory for this Mac2 Driver to be selected
        'automationName': 'Mac2',
        'platformName': 'mac',
        'bundleId': 'com.apple.TextEdit',
    })
    yield drv
    drv.quit()


def test_edit_text(driver):
    edit_field = driver.find_element_by_class_name('XCUIElementTypeTextView')
    edit_field.send_keys('hello world')
    assert edit_field.text == 'hello world'
    edit_field.clear()
    assert edit_field.text == ''


def test_sending_custom_keys(driver):
    edit_field = driver.find_element_by_class_name('XCUIElementTypeTextView')
    flagsShift = 1 << 1
    driver.execute_script('macos: keys', {
        'keys': [{
            'key': 'h',
            'modifierFlags': flagsShift,
        }, {
            'key': 'i',
            'modifierFlags': flagsShift,
        }]
    })
    assert edit_field.text == 'HI'
```

## このあと

Appium desktop を使用して, TextEditor 上の element を確認したりして, コードを追加していけば自動による操作を追加できます