---
title: Appium で screen recordを使用する
date: 2021-03-03
tags: Appium
ArticleID: 20210303
---

Official な document では少々不足していたので, 使い方をまとめます.

```python
self.driver.start_recording_screen()

payload = self.driver.stop_recording_screen()

# ★この2行
with open('video.mp4', "wb") as fd:
    fd.write(base64.b64decode(payload))

```

# 使用用途

## Azure pipeline にて
Azure pipelineではテストが失敗したときになぜ失敗したのか追いにくいため, screen recordで動画を取得しておくとよいです

参考: https://github.com/appium/python-client/blob/master/test/functional/android/helper/test_helper.py

# Links
* https://appium.io/docs/en/commands/device/recording-screen/start-recording-screen/
* https://appium.io/docs/en/commands/device/recording-screen/stop-recording-screen/
