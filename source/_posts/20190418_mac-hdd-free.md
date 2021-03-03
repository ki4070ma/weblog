---
title: Macで空き容量を増やすためにやったこと
date: 2019-04-18
tags: Mac
---

1. まずどこで容量を食っているの確認
    * OmniDiskSweeper
    * https://www.omnigroup.com/more/

2. Dockerあたりで容量を食っていた
    * $docker system prune -f
    * Docker.rawが大きくなっていたので削除
        * https://forums.docker.com/t/where-does-docker-keep-images-containers-so-i-can-better-track-my-disk-usage/8370/11
        * $rm ~/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux
        * rm ~/Library/Containers/com.docker.docker/Data/vms/0/Docker.raw (2019/04/18, Pathは変わることがある?)
    * [効果] 人による. docker使ってる人で同じように困っている人はたくさんいたので調べるといろいろ出てくる

3. Mac関連
    * $brew cleanup -s 

4. Mac ストレージの空き領域を増やす方法 (Apple公式)
    * https://support.apple.com/ja-jp/HT206996

5. その他
    * Xcodeが大きい...
    * そもそも大きな容量を積んだMacbookを買いましょう (反省)

ref: https://qiita.com/atsushi0521/items/85aca0153c33a22e74a3