---
title: Azure pipeline で Appium を走らせて, Android, iOS のテストを走らせる
date: 2021-03-09
tags: [Azure, Appium, Android, iOS, Python]
---

Azure pipeline で Appium を走らせて, Android, iOS のテストを走らせることができます

## Azure pipelines 

オープンソースプロジェクトであれば時間制限なしで無料で使用できます

https://azure.microsoft.com/ja-jp/services/devops/pipelines/

以下は以前contributeしたものです
まずは `azure-pipelines.yml` を以下のように書いて, 実体は `./ci-jobs/functional_test.yml` にあります

{% ghcode https://github.com/appium/python-client/blob/e49dc784d376145f12afe2f61a8ee7348c2ee08e/azure-pipelines.yml 5 6 %}

このあたりで必要なパラメータを設定しています

{% ghcode https://github.com/appium/python-client/blob/e49dc784d376145f12afe2f61a8ee7348c2ee08e/ci-jobs/functional_test.yml 1 6 %}

* vmImage: コマンドを実行していくマシンのOSです
* pytestOpt: pytest の option
* androidSdkVer: 使用するAndroid SDK ver. 作成する Emulator の OS に影響します
* xcodeForIOS: 使用する xcode ver. 作成する Simulator の iOS に影響します

### Appium を走らせる

実体は `functional/run_appium.yml` に

{% ghcode https://github.com/appium/python-client/blob/e49dc784d376145f12afe2f61a8ee7348c2ee08e/ci-jobs/functional/run_appium.yml %}

ざっくり

* node インストール
* npm で appium をインストール
* (必要に応じて opencv4nodejs をインストール)
* ffmpeg インストール (screen recordするために必要)
* appium-python-client をインストール
* pip で dependency の解消
* インストールしたものの ver 一覧列挙
* appium を走らせる

### iOS

実体は `./functional/run_ios_test.yml` に

{% ghcode https://github.com/appium/python-client/blob/e49dc784d376145f12afe2f61a8ee7348c2ee08e/ci-jobs/functional/ios_setup.yml %}

こちらでは Simulator を起動するために xcode の ver を指定
iOS についてはテストを走らせる中で Simulator が起動するようになっているので, あとは pytest でテストを走らせるだけで ok 

### Android

実体は `./functional/run_android_test.yml` に

{% ghcode https://github.com/appium/python-client/blob/e49dc784d376145f12afe2f61a8ee7348c2ee08e/ci-jobs/functional/start-emulator.sh %}

こちらでは Android Emulator を起動しています
元となっているファイルは azure pipelines 公式からもってきています

この後に pytest でテスト走らせることができます

### Tips

Azure pipeline でテストを実行して, 失敗したとき, なぜ失敗しているか追いにくいので, screen record (画面録画)を取得するようになっているのでそちらも参考に