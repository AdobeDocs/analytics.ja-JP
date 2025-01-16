---
title: 基本関数
description: 計算指標ビルダーを使用すると、統計関数と数学関数を適用して、高度な計算指標を作成できます。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 6c707a154447d4b419cc6af8b9ddd2d5d0255072
workflow-type: tm+mt
source-wordcount: '1636'
ht-degree: 100%

---

# 基本関数


[計算指標ビルダー](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)では、統計関数および数学関数を適用できます。この記事では、関数とその定義をアルファベット順に示します。

>[!NOTE]
>
>[!DNL metric] が関数の引数として特定されている場合は、指標の他の式も許可されます。例えば、[COLUMN MAXIMUM(metrics)](#column-maximum) を [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum) としてもかまいません。



## 表関数と行関数

表関数とは、表のどの行についても出力が同じになる関数です。行関数とは、表の各行で出力が異なる関数です。

該当する場合および関連する場合、関数には、関数のタイプで注釈が付けられます。[!BADGE テーブル]{type="Neutral"}[!BADGE 行]{type="Neutral"}

## ゼロを含むパラメーターとは

このパラメーターは、計算にゼロを含むかどうかを示します。ゼロは&#x200B;*何もない*&#x200B;ことを意味する場合もあれば、重要な意味を持つ場合もあります。

例えば、売上高の指標がある場合に、ページビュー数の指標をレポートに追加すると、すべてゼロの売上高の行が突然表示されます。その追加の指標が **[MEAN](cm-functions.md#mean)**（平均値）、**[ROW MINIMUM](cm-functions.md#row-min)**（行の最小値）、**[QUARTILE](cm-functions.md#quartile)**（四分位数）および売上高列にあるその他の計算に影響を与えることは避けるべきです。この場合は、`include-zeros` パラメーターを確認します。

別のシナリオとして、2 つの目標指標があり、一方の指標の平均または最小値が高くなるのは、一部の行がゼロであるためです。その場合、パラメーターにゼロを含めるかどうかを確認しないことを選択できます。



## 絶対値 {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="絶対値"
>abstract="数の絶対値を返します。数の絶対値とは、正の値を持つ数です。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | 絶対値を求める指標です。 |


## 列の最大値 {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="列の最大値"
>abstract="指標列の一連のディメンション要素の中の最大値を返します。MAXV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

指標列の一連のディメンション要素の中の最大値を返します。MAXV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 列の最小値 {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="列の最小値"
>abstract="指標列の一連のディメンション要素の中の最小値を返します。MINV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

指標列の一連のディメンション要素の中の最小値を返します。MINV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 列の合計値 {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="列の合計値"
>abstract="（1 つのディメンションの複数の要素の）1 つの列内の指標のすべての数値を加算します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

（1 つのディメンションの複数の要素の）1 つの列内の指標のすべての数値を加算します。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |


## カウント {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="カウント"
>abstract="1 つの列内の指標のゼロ以外の値の数（カウント）（ディメンション内でレポートされた一意の要素の数）を返します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | カウントする指標です。 |


## 指数 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="指数"
>abstract="指定された数の指数（e）を返します。定数 e は 2.71828182845904 と等しく、これは自然対数の底です。EXPONENT（指数）は LN（数の自然対数）の逆関数です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | 底 e に適用される指数です。 |


## 平均 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="平均"
>abstract="1 つの列の指標の算術平均（平均値）を返します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | 平均を求める指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 中央値 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="中央値"
>abstract="1 つの列の指標の中央値を返します。中央値は、一連の数の中央にある数値です。つまり、数の半分は中央値よりも大きいか等しい値であり、残りの半分は中央値よりも小さいか等しい値です。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | 中央値を求める指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## モジュロ {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="モジュロ"
>abstract="ユークリッド除法 で x を y で割った余りを返します。 "

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

ユークリッド除法 で x を y で割った余りを返します。

| 引数 | 説明 |
|---|---|
| metric_X | 除算する最初の指標。 |
| metric_Y | 除算する 2 番目の指標。 |

### 例

返される値の符号は入力した値の符号と同じです（またはゼロが返されます）。

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

常に正の数を求めるには、次の構文を使用します。

```
MODULO(MODULO(x,y)+y,y)
```

## パーセンタイル {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="パーセンタイル"
>abstract="0～100 の値である、n 番目のパーセンタイルを返します。n &lt; 0 の場合、関数は 0 を使用します。n > 100 の場合、関数は 100 を返します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | 0 ～ 100（0 と 100 を含む）の範囲のパーセンタイル値です。 |
| k | 相対的な値を定義する指標列です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |



## 累乗演算子 {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="累乗演算子"
>abstract="x の y 乗を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

x の y 乗を返します。

| 引数 | 説明 |
|---|---|
| metric_X | metric_Y の累乗に上げる指標です。 |
| metric_Y | metric_X を何乗まで上げるかを示します。 |


## 四分位数 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="四分位数"
>abstract="指標の値の四分位数を返します。例えば、四分位数を使用して、最も売上高の多い上位 25 ％の製品を探すことができます。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE テーブル]{type="Neutral"}[COLUMN MINIMUM](#column-minimum)、[MEDIAN](#median)、および [COLUMN MAXIMUM](#column-maximum) は、四分位数がそれぞれ `0`（ゼロ）、`2`、`4` に等しい場合、[QUARTILE](#quartile) と同じ値を返します。

| 引数 | 説明 |
|---|---|
| 指標 | 四分位数値を求める指標です。 |
| 四分位数 | 四分位数として返す値を示します。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 四捨五入 {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="四捨五入"
>abstract="*数値*&#x200B;パラメーターのない四捨五入は、*数値*&#x200B;パラメーターが 0 の四捨五入と同じで、直近の整数に四捨五入します。*数値*&#x200B;パラメーターがある場合、ROUND は小数点の右側に&#x200B;*数*&#x200B;桁を返します。*数*&#x200B;が負数の場合、小数点の左側に 0 が返されます。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

*数値*&#x200B;パラメーターのない四捨五入は、*数値*&#x200B;パラメーターが 0 の四捨五入と同じで、直近の整数に四捨五入します。*数値*&#x200B;パラメーターがある場合、ROUND は小数点の右側に&#x200B;*数*&#x200B;桁を返します。*数*&#x200B;が負数の場合、小数点の左側に 0 が返されます。

| 引数 | 説明 |
|---|---|
| 指標 | 四捨五入する指標です。 |
| 数 | 小数点の右側に返す桁数。（負の数が小数点の左側に 0 を返す場合）。 |

### 例

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## 行数 {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="行数"
>abstract="指定された列の行の数（ディメンション内でレポートされた一意の要素の数）を返します。*超過したユニーク数*&#x200B;は 1 としてカウントされます。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

指定された列の行の数（ディメンション内でレポートされた一意の要素の数）を返します。*超過したユニーク数*&#x200B;は 1 としてカウントされます。


## 行の最大値 {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="行の最大値"
>abstract="各行の列の最大値。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

各行の列の最大値。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 行の最小値 {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="行の最小値"
>abstract="各行の列の最小値。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

各行の列の最小値。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |



## 行の合計 {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="行の合計"
>abstract="各行の列の合計。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

各行の列の合計。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |


## 平方根 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="平方根"
>abstract="数の正の平方根を返します。数の平方根は、2 乗してその数になる値です。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | 平方根を求める指標です。 |


## 標準偏差 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="標準偏差"
>abstract="データのサンプル母集団に基づいて標準偏差（平方偏差の平方根）を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| | 標準偏差を求める指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 平方偏差 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="平方偏差"
>abstract="データのサンプル母集団に基づいて平方偏差を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| 指標 | 平方偏差を計算する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


VARIANCE の式は次のようになります。

![](assets/variance_eq.png){width="100"}

ここで、*x* はサンプルの平均値 [MEAN(*metric*)](#mean) であり、*n* はサンプルサイズです。


平方偏差を計算するには、数字の列全体を見ます。まず、すべての数字の平均を求めます。平均を求めたら、各数字に対して次の計算を行います。

1. 数字から平均を減算します。

1. 結果を 2 乗します。

1. その結果を合計に加算します。

この計算をすべての列に対して実行したら、1 つの合計を求めます。その合計を列内にある数字の個数で除算します。その結果が列の平方偏差です。平方偏差は単一の数字です。ただし、数字の列として表示されます。

次の 3 項目列の例では、

| 列 |
|:---:|
| 1 |
| 2 |
| 3 |

この列の平均は 2 です。この列の平方偏差は、((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3 です。

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->