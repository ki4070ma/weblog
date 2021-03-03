---
title: WeMo Insightで現在の消費電力を取得する
date: 2018-01-13
tags: WeMo
---

# WeMo Insight
* こういうもの↓で, アプリ経由でACオンオフできたり, 消費電力確認できる
  * [Wemo® Insight Smart Plug(Official)](http://www.belkin.com/us/p/P-F7C029/)
  * [WeMo app (Android)](https://play.google.com/store/apps/details?id=com.belkin.wemoandroid&hl=ja), iOSアプリもあり

# API
* この機器をCLIやPython API経由で操作できたりする
    * https://github.com/iancmcc/ouimeaux
        * ドキュメント: http://ouimeaux.readthedocs.io/en/latest/
            * [インストール](http://ouimeaux.readthedocs.io/en/latest/installation.html)
            * [CLI](http://ouimeaux.readthedocs.io/en/latest/wemo.html)
            * [Python API](http://ouimeaux.readthedocs.io/en/latest/api.html)

# WeMo Insightの現在の消費電力を知る手順
* だいたい上記のPython APIに書いてあることです

```
pi@raspberrypi:~ $ python
Python 2.7.13 (default, Nov 24 2017, 17:33:09) 
[GCC 6.3.0 20170516] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> from ouimeaux.environment import Environment
>>> def on_switch(switch):
...   print "Switch found!", switch.name
... 
>>> def on_motion(motion):
...   print "Motion found!", motion.name
... 
>>> env = Environment(on_switch, on_motion)
>>> env.start()
>>> env.discover(seconds=3)
Switch found! WeMo
>>> env.list_switches()
['WeMo']
>>> switch = env.get_switch('WeMo')
>>> switch
<WeMo Insight "WeMo">
>>> print switch.get_state()
0
>>> switch.on()
>>> print switch.get_state()
1
>>> print switch.insight_params
{'onfor': 51, 'state': '8', 'ontotal': 16144, 'totalmw': 40961936, 'ontoday': 16499, 'todaymw': 40961936, 'lastchange': datetime.datetime(2018, 1, 13, 13, 4, 24), 'currentpower': 0}
>>> print switch.insight_params['currentpower']
0 (WeMoに何も差してない状態)
>>> print switch.insight_params['currentpower']
15915 (WeMoにノートPCのACアダプタを差している)
```

ref: https://qiita.com/atsushi0521/items/28355e9d789a07c61f2f