R入門いろはにほへと: RStudioを使った実践
========================================================
author: 瓜生真也（横浜国立大学大学院環境情報学府）
date: June 30, 2014 @ Yokohama.R#1
font-family: 'Helvetica'
autosize: true
css: custom.css



RStudioのインストール
=====

Rの統合開発環境... もっと便利にRを使える

http://www.rstudio.com

![](https://github.com/YokohamaR/yokohama.r/wiki/src/images/installation-rstudio.gif)

RStudioのインストール
=====

![](https://github.com/YokohamaR/yokohama.r/wiki/src/images/startup-rstudio.png)

準備
=====

1. デスクトップに**`first-practice-r`**というフォルダを新規作成
2. RStudioの起動
    * Tools -> Global Options -> PackagesでCRAN mirorをJapan(Tokoy)に設定    
    * 作業ディレクトリの設定
        * `setwd("C:Users/****/Desktop/first-practice-r/")`
    * 新規ファイルの作成 File -> New File -> R Markdownを選択
        * **`practice-名前（イニシャルなど）.R`**として一旦保存

操作方法のおさらい
=====


```r
1 + 3
```

```
[1] 4
```

```r
a <- c(1, 2, 3)
b <- c(4, 5, 6)
a + b
```

```
[1] 5 7 9
```

```r
a * b
```

```
[1]  4 10 18
```

操作方法のおさらい
=====


```r
mean(b)
```

```
[1] 5
```

```r
10 * pi
```

```
[1] 31.42
```

パッケージのインストール
=====

パッケージ -> Rの機能を拡張させるもの。たくさんあります！

CRANからダウンロード

* `install.packages("パッケージ名", dependencies=T)`
* メニューバー Tools -> Install Packages ... 不安定？

これから使用するパッケージをインストール

* `knitr`: RMarkdownで作成したファイルをHTMLファイルに変換したり...
* `lattice`: 強力な作図のためのパッケージ
* `devtools`: CRAN以外からパッケージをインストールする場合などに必要



irisデータの図示と保存
====


```r
data(iris)
```


```r
head(iris)
```


```r
png("ex_iris_plot") # ファイル名
plot(
  iris$Sepal.Length, iris$Petal.Length, 
  col=c("royal blue", "green", "orange")[iris$Species], 
  pch=16, cex=2)
dev.off() #必ずつけること
```

<img src="https://github.com/YokohamaR/yokohama.r/wiki/src/images/ex_iris_plot.png" width=300 align=right>

ファイルの読み込み
====

[https://github.com/YokohamaR/first-practice-r/](https://github.com/YokohamaR/first-practice-r/)　から**`sample-data.csv`**をダウンロード


```r
df <- read.csv("sample-data.csv", header=T)
summary(df)
```

その他
=====

本日の内容はこんなところです。

要望あれば追加でやります！
