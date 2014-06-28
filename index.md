R入門いろはにほへと: インストールから簡単な操作まで
========================================================
author: 瓜生真也（横浜国立大学大学院環境情報学府）
date: June 30, 2014
font-family: 'Helvetica'
autosize: true
css: custom.css



CONTENTS
=====

1. Rの概要
2. Rのインストール
3. 簡単な操作
4. RStudioのインストール

Rの概要
========================================================
<img src="https://raw.githubusercontent.com/uribo/rep-res-guideline/master/src/r-logo.png" widht="30" align="right"/>

多くの研究分野で使用される統計解析環境ソフト

* **オープンソース**なので、どういう機能を持っているのかがわかりやすい
* **フリーソフトウェア**。他の統計解析ソフトの多くが高価
* **パッケージ**と呼ばれる拡張機能により、多くの機能を増やせる

Rのインストール
=====

### -> [CRAN](http://cran.r-project.org)

Downlaod R for **Linux/Mac/Win**

Windowsの場合...

![](https://github.com/YokohamaR/yokohama.r/wiki/src/images/20140606-081254_capture.gif)

Rスクリプトの書き方
=====


```r
1 + 3
```

```
[1] 4
```


```r
a <- c(1, 2, 3)
a
```

```
[1] 1 2 3
```


```r
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

Rスクリプトの書き方
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

Andersonのアヤメのデータを使った例
======

> 三種類のあやめの品種のそれぞれからの50の花の蕚(がく)片の長さと幅、花弁の長さと幅


```r
data(iris)
head(iris)
```

```
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
6          5.4         3.9          1.7         0.4  setosa
```

Fisherのアヤメのデータを使った例
======

#### 図を描く


```r
plot(
  iris$Sepal.Length, iris$Petal.Length, 
  col=c("royal blue", "green", "orange")[iris$Species], 
  pch=16, cex=2)
```

![](https://github.com/YokohamaR/yokohama.r/wiki/src/images/ex_iris_plot.png)

関数とパッケージ
=====

一元配置分散分析... `oneway.test()`

> ３種の萼片の長さの平均値に差があるか


```r
oneway.test(iris$Sepal.Length ~ iris$Specie)
```

```

	One-way analysis of means (not assuming equal variances)

data:  iris$Sepal.Length and iris$Specie
F = 138.9, num df = 2.00, denom df = 92.21, p-value < 2.2e-16
```

> P < 0.001で萼片の長さの平均値には３種間で差がある


関数とパッケージ
=====

```r
install.package("lattice", dependencies=TRUE)
```


```r
library(lattice)
xyplot(
  Petal.Length ~ Sepal.Length | Species,
  data=iris)
```

![](https://github.com/YokohamaR/yokohama.r/wiki/src/images/ex_iris_xyplot.png)

RStudioのインストール
=====

http://www.rstudio.com

![](https://github.com/YokohamaR/yokohama.r/wiki/src/images/installation-rstudio.gif)

RStudioのインストール
=====

![](https://github.com/YokohamaR/yokohama.r/wiki/src/images/startup-rstudio.png)
