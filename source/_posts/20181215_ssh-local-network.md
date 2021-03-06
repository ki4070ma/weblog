---
title: ローカルネットワーク内でsshするための設定
date: 2018-12-15
tags: [ssh, Technology]
---

自分が調べたことのメモ, ほぼどこかへのリンク.

# やろうとしたこと
* 家のローカルネットワーク内に繋がれている以下の機器間でsshでログインする
    * Raspberry Pi
    * Ubuntu 16.04
    * Mac

# 使用しているWi-Fiルーター 
* Buffalo WSR-300HP/N
    * はじめssh出来るようにするにはルータの設定が必要かと思ったがそうではなかった

# Raspberry Piの設定
* [SSH (Secure Shell)](https://www.raspberrypi.org/documentation/remote-access/ssh/) (英語. Raspberry Pi 公式)
    * qiitaで調べたものはうまくいかなったものが多かった

```
    1. Enter sudo raspi-config in a terminal window
    2. Select Interfacing Options
    3. Navigate to and select SSH
    4. Choose Yes
    5. Select Ok
    6. Choose Finish
```

* 上記の設定で, Ubuntu/Mac -> Raspberry Piへのsshのログインが可能になった

# Macの設定
* [リモートコンピュータに Mac へのアクセスを許可する](https://support.apple.com/ja-jp/guide/mac-help/mchlp1066/mac)
* 上記の設定でUbuntu/Raspberry Pi -> Macへのsshのログインが可能になった.

# Ubuntuの設定
* [Ubuntuでsshdの設定をしてリモートから接続できるようにする](http://d.hatena.ne.jp/Fiore/20080228/1204174833)
* 今のところうまく行ってない, うーむ

ref: https://qiita.com/atsushi0521/items/80e36b1d8d7306ee2357
