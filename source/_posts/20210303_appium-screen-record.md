---
title: Appium で screen recordを使用する
date: 2021-03-03
tags: [Appium, Python, Technology]
---

<!-- toc -->

Official な document では少々不足していたので, 使い方をまとめます.

```python
self.driver.start_recording_screen()

payload = self.driver.stop_recording_screen()

# ★この2行
with open('video.mp4', "wb") as fd:
    fd.write(base64.b64decode(payload))

```

# 使用用途

## ローカル実行にて
ローカル実行であれば実際に目で見ての確認で十分かもしれません
しかし, 不具合起票時に他の人に見せるときなどに screen record があれば, そちらを元にやりとりできればコミュニケーションコストを下げることができます.

## Azure pipeline にて
Azure pipelineではテストが失敗したときになぜ失敗したのか追いにくいため, screen record で動画を取得しておくとよいです
その後は azure pipeline の artifact から動画を取得して実際にテストを走らせているときの端末の画面を録画した動画を確認することができます

参考: https://github.com/appium/python-client/blob/master/test/functional/android/helper/test_helper.py

# Links
* https://appium.io/docs/en/commands/device/recording-screen/start-recording-screen/
* https://appium.io/docs/en/commands/device/recording-screen/stop-recording-screen/
