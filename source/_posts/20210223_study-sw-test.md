---
title: Software test に関する Slideshare
date: 2021-02-23
tags: [Study, SoftwareTest, Slideshare]
---

* Black box testing
	* http://www.slideshare.net/abasit83/black-box-testing-30782934
		* What is dynamic black-box testing?
		* How to reduce the number of test cases by equivalence partitioning
		* How to identify troublesome boundary conditions
		* Good data values to use to induce bugs
		* How to test software states and state transitions
		* How to use repetition, stress, and high loads to locate bugs
		* A few secret places where bugs hide
		* [感想]
			* Specないときに, Spec知るためのExploratory testing
			* **Test-to-pass** -> 最低限の動作を確認するため(Normal)
			* **Test-to-fail** -> バグを出させるためのテスト
			* **Equivalence Partitioning** -> 入力/出力/操作の同値グループを作る
				* 計算機とか, 1+1, 1+2, 10+12, 100+102, ...無限にあるし
				* テストデータの数を減らすため
	* http://www.slideshare.net/nivetha/black-box-testing
		* Developerがやらないのはなぜ?
			* 自分が作ったコードを壊すのは難しいから. (Disagree by Mori)
		* テストデータの種類
			* Valid
			* Invalid
			* Boundary
		* Error Guessing
			* 経験と勘から
		* [例] バイクが止まったときなに確認する? ガソリン? 整備士さんとこ行く? マニュアル, spark plug

* White box testing
	* http://www.slideshare.net/oanafeidi/whitebox-testing-11958709
		* デザインや実装にフォーカスするのではなく、実装のロジックにフォーカス
		* Test case selection is based on an analysis of the internal structure of component
		* ちょっと良くわからない
	* http://www.slideshare.net/himanshuhora/white-box-black-box-gray-box-testing
		* テストケースをデザインするために使われる
		* white box testing はコードのスキルが必要
	* http://www.slideshare.net/wdelzein/black-white-box-testing
		* White boxとBlack boxの使い分け
		* P.14
		* [Unit test] : **White** box
			* Unit level
		* [Integration] : **White** box & **Black** box
			* Multiple classes
		* [Functional] : **Black** box
			* Whole product
		* [System] : **Black** box
			* Requirements analysis
			* Whole product in representative environments
		* [Acceptance] : **Black** box
			* Requirements analysis
			* Whole product in customers's environments
		* [Beta] : **Black** box
			* Adhoc
		* [Regression] : **Black** box & **White** box
