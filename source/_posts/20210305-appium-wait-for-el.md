---
title: Appiumで特定のelementが表示されるまで待つ
date: 2021-03-05
tags: Appium
---

# 必要な背景

以下のようなケースで役に立ちます

* (特にAndroid) 端末の動作が遅い時などに画面遷移で時間がかかるとき
* ネットワークの状態によって待ちが発生するとき

Azure pipeline上のAndroid emulatorでAppiumを動作させるときに活躍しました

# Sample code

以前自身で作成したコードです (contribution)
https://github.com/appium/python-client/blob/master/test/functional/test_helper.py

```python

from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

def wait_for_element(driver: 'WebDriver', locator: str, value: str, timeout_sec: float = 10) -> 'WebElement':
    """Wait until the element located
    Args:
        driver: WebDriver instance
        locator: Locator like WebDriver, Mobile JSON Wire Protocol
            (e.g. `appium.webdriver.common.mobileby.MobileBy.ACCESSIBILITY_ID`)
        value: Query value to locator
        timeout_sec: Maximum time to wait the element. If time is over, `TimeoutException` is thrown
    Raises:
        `selenium.common.exceptions.TimeoutException`
    Returns:
        The found WebElement
    """
    return WebDriverWait(driver, timeout_sec).until(EC.presence_of_element_located((locator, value)))

# 'Bouncing Balls' というテキストを持つelementを待つ処理. 返り値は検出したelement.
el = wait_for_element(self.driver, MobileBy.ACCESSIBILITY_ID, 'Bouncing Balls')

```