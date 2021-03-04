---
title: Appiumのセットアップ, 使い方
date: 2019-01-01
tags: Appium
---

# Appiumのセットアップ
* Node
    * https://nodejs.org/en/
    * Appiumインストールのため

* Appium
    * 公式
        * http://appium.io/docs/en/about-appium/getting-started/?lang=en
    * [$npm install -g appium] Permission deniedでインストール失敗した
        * [解決方法] https://stackoverflow.com/questions/48910876/error-eacces-permission-denied-access-usr-local-lib-node-modules-react?rq=1
    * [JDK インストール] https://www.oracle.com/technetwork/java/javase/downloads/index.html
    * [$npm install -g appium-doctor] Appium-doctor
        * appiumを使うために不足している設定を診断してくれる
    * 必要だった設定
        * Please install Carthage. Visit https://github.com/Carthage/Carthage#installing-carthage for more information.
        * Manually configure ANDROID_HOME.
        * Manually configure JAVA_HOME.
            * こんな風に指定できるらしい. https://qiita.com/seri_k/items/e978c1339ce51f13e297
        * Manually configure ANDROID_HOME and run appium-doctor again.

```
export ANDROID_HOME="~/Library/Android/sdk"
export JAVA_HOME=`/usr/libexec/java_home -v 11`
export PATH=$JAVA_HOME/bin:$PATH
```

* Appium desktop
   * https://github.com/appium/appium-desktop

# 使い方

## Screenrecord
[Appium で screen recordを使用する](/20210303_appium-screen-record/)


# Memo
* 試してみる: appium-docker-android
    * https://github.com/appium/appium-docker-android
    * なぜか上手く動かなかった

ref: https://qiita.com/atsushi0521/items/660a3ac74cb4b7d734f5