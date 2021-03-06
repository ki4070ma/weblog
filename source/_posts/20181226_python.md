---
title: PythonのLibraryで使用したことがあるもの
date: 2018-12-26
tags: [Python, Technology]
---

<!-- toc -->

使用したことがあるlibraryに加えて一言

# どんなライブラリたちがあるか
* https://github.com/vinta/awesome-python
    * awesome系はよくまとまっています

# OSSライブラリ一覧

* ansible
    * https://github.com/ansible/ansible
    * 構成管理ツール
    * [メモ] fabricよりも自由度がないイメージ. ただ自由度がないということがメンテナンス的にメリット, とコメントしている方がいた. あまりきちんと使っていない. github上のstarはfabricより多い
* Fabric
    * https://github.com/fabric/fabric
    * 構成管理ツール
    * [メモ] ansibleよりも何でもできる(イメージ). ただ, 何でもできるが故にスクリプトのメンテナンスはやりづらくなる印象. 出来る限りansibleで対応するほうがいいのか...
* Appium-Python-Client
    * https://github.com/appium/python-client
    * [メモ] appiumのテストスクリプトをpythonで書くためのclient. appiumはいろんな言語で書けるから素敵.
* beautifulsoup4
    * https://pypi.org/project/beautifulsoup4/
    * [メモ] "Beautiful Soup is a library that makes it easy to scrape information from web pages."です. htmlのファイルから取り出したい要素を特定して抜き出します.
* chainer
    * https://github.com/chainer/chainer
    * [メモ] Deep learningですね. まだ使ってないです...使います
* Jinja2
    * https://github.com/pallets/jinja
    * [メモ] Python用のテンプレートエンジン. Fabricでテンプレをagentにアップロードするときに使用した. こんな便利なものもあるものなんだ
* matplotlib
    * https://github.com/matplotlib/matplotlib
    * [メモ] グラフが書けます. (あまり凝ったグラフは書いてませんが)
* mysql-connector-python
    * https://pypi.org/project/mysql-connector-python/
    * [メモ] PythonからMySQLのDBを操作する
* netifaces
    * https://github.com/al45tair/netifaces
    * [メモ] pythonのコードからNICやIP addrが取得したいときに使う
* numpy
    * https://github.com/numpy/numpy
    * [メモ] 行列やらなんやら. RGBの配列をOpenCVを使って画像生成など
* opencv
    * https://github.com/skvark/opencv-python
    * https://pypi.org/project/opencv-python/
    * [メモ] 説明不要な画像処理ライブラリのOpenCV. 画像処理をやっている人はみな知っているのでは. webcamから入ってくる画像に対して処理をしたり, オプティカルフローで遊んだり, etc そんなにすごい使い方はしてません.(きっぱり)
* ouimeaux
    * https://github.com/iancmcc/ouimeaux
    * [メモ] "Python API to Belkin WeMo devices"です. これがあればコマンドラインやpythonのプログラムから機器を操作できます.
* pandas
    * https://github.com/pandas-dev/pandas
    * [メモ] "Flexible and powerful data analysis"です. あまりたくさん使ったわけではないが, Excel上で出来ることを変わりにやってた.
* pit
    * https://github.com/yoshiori/pit
    * [メモ] ID / Passwordを直接コードに書かなくていいように
* pyalsaaudio
    * https://github.com/larsimmisch/pyalsaaudio/
    * [メモ] "ALSA wrappers for Python", that's it
* pyserial
    * https://pythonhosted.org/pyserial/
    * https://github.com/pyserial/
    * [メモ] Serial port経由のデータのread/writeを行うときに使用した
        * https://en.wikipedia.org/wiki/Serial_port
* TestLink-API-Python-client
    * https://github.com/lczub/TestLink-API-Python-client
    * [メモ] 自分で立てたTestLinkサーバからデータを取得するために使用した

## Test framework
* nose
    * https://github.com/nose-devs/nose
    * [メモ] pytestより人気らしい. githubのstartは1/3くらい. pytestって名前が強いよね
        * https://sekailab.com/wp/2016/07/18/python-test/#pytest_vs_nose_vs_unittest
* pytest
    * https://github.com/pytest-dev/pytest
    * [メモ] テストを走らせる場合はこれ, らしい. 少しのメリットしか享受できていないので, より把握してメリットを享受する


## Coding guidelineなどの静的解析
* pyflakes
    * https://github.com/PyCQA/pyflakes
    * [メモ] 
* autopep8
    * https://github.com/hhatto/autopep8
    * [メモ] "A tool that automatically formats Python code to conform to the PEP 8 style guide.", これに尽きます. 改行が想定していないところでも入るのがなんとも.
* pylint
    * https://github.com/PyCQA/pylint
    * [メモ] 言わずと知れたlinter

## ツール
* gprof2dot
    * https://github.com/jrfonseca/gprof2dot
    * [メモ] 自身が作成したプログラムのパフォーマンスを計測したときに使用した, profileのファイルを可視化してくれるツール

# 組み込み
* argparse
    * https://docs.python.jp/3/library/argparse.html
    * [メモ] 引数をいろいろ設定したいときに使う. これは便利
* pprint
    * https://docs.python.jp/3/library/pprint.html
    * [メモ] 込み入った辞書型を綺麗に出力するにはこれ
* subprocess
    * https://docs.python.org/ja/3/library/subprocess.html
    * [メモ] 困ったらなんでもこれ使っていた. が, まず組み込みAPIに無いかを探しましょう(lsじゃなくてglobとか)
* glob
    * https://docs.python.jp/3/library/glob.html
    * [メモ] subprocessでls, ではなくこれを使いましょう
* pickle
    * https://docs.python.jp/3/library/pickle.html
    * [メモ] python objectをファイルへ出力. 永続化したいものとか.

ref: https://qiita.com/atsushi0521/items/13972fa54039854027e1