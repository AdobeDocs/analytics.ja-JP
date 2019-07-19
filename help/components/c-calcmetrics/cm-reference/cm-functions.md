---
description: 計算指標ビルダーを使用すると、統計関数と数学関数を適用して、高度な計算指標を作成できます。
seo-description: 計算指標ビルダーを使用すると、統計関数と数学関数を適用して、高度な計算指標を作成できます。
seo-title: 基本関数の参照
title: 基本関数の参照
uuid: 5c2b4a0e-613c-4b27-95b8-01d480aab78
translation-type: tm+mt
source-git-commit: a4ccd3503d9d8e5e5367bb1ebd149262c5cb925a

---


# リファレンス:基本関数

<!-- 

cm_functions.xml

 -->

計算指標ビルダーを使用すると、統計関数と数学関数を適用して、高度な計算指標を作成できます。

ここでは、関数とその定義をアルファベット順に示します。

>[!NOTE]
>
>Where [!DNL metric] is identified as an argument in a function, other expressions of metrics are also allowed. For example, [!DNL MAXV(metrics)] also allows for [!DNL MAXV(PageViews + Visits).]

## 表関数と行関数 {#section_8977BE40A47E4ED79EB543A9703A4905}

表関数とは、表のどの行についても出力が同じになる関数です。行関数とは、表の各行で出力が異なる関数です。

## 絶対値（行）{#concept_4CC47884F7CA49D5B84AC898EA596673}

数の絶対値を返します。数の絶対値とは、正の値を持つ数です。

```
ABS(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 絶対値を求める指標です。 |

## 列の最大値 {#concept_B25518D717D24F82B65CDE49A153D3A3}

指標列の一連のディメンション要素の中の最大値を返します。MAXV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。

```
MAXV(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 評価する指標です。 |

## 列の最小値 {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

指標列の一連のディメンション要素の中の最小値を返します。MINV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。

```
MINV(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 評価する指標です。 |

## 列の合計値 {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

（1 つのディメンションの複数の要素の）1 つの列内の指標のすべての数値を加算します。

```
SUM(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 合計値を求める指標です。 |

## カウント（表）{#concept_2C6ED2B88AB74481BD130969FB071A41}

1 つの列内の指標のゼロ以外の値の数（カウント）（ディメンション内でレポートされた一意の要素の数）を返します。

```
COUNT(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | カウントする指標です。 |

## 指数（行）{#concept_17554F9D234449FB8DDEE895816B3FF1}

指定された数の指数（*e*）を返します。定数 *e* は 2.71828182845904 と等しく、これは自然対数の底です。EXP は LN（数の自然対数）の逆関数です。

```
EXP(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 底 *e* に適用される指数です。 |

## 累乗法 {#concept_941578534F1E4583B1BEB067C8113A21}

累乗演算子

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)
</pre>

## 平均値（表）{#concept_F4FF950580304D0B99DA7FBB5DB8730A}

1 つの列の指標の算術平均（平均値）を返します。

```
MEAN(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 平均を求める指標です。 |

## 中央値（表）{#concept_183EC31208524EDB8463D986DE2E895F}

1 つの列の指標の中央値を返します。中央値とは、一連の数の中央に位置する数です。つまり、半分の数は中央値以上の値を持ち、残りの半分は中央値以下の値を持ちます。

```
MEDIAN(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 中央値を求める指標です。 |

## 剰余 {#concept_DE0825D7A51643219CB01F59667EA352}

ユークリッドの割り算を使用した場合の col1 / col2 の余りです。

x を y で割った余りを返します。

```
x = floor(x/y) + modulo(x,y)
```

返される値の符号は入力した値の符号と同じです（またはゼロが返されます）。

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

常に正の数を求めるには、次の構文を使用します。

```
modulo(modulo(x,y)+y,y)
```

## パーセンタイル（表）{#concept_51DF57B606D14F898E5010DBA61CA979}

指標の値の k 番目のパーセンタイルを返します。この関数を使用すると、受け入れのしきい値を確立できます。例えば、90%の割合を超えるディメンションエレメントを調べることができます。

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> 相対的な値を定義する指標列です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> 0 ～ 100（0 と 100 を含む）の範囲のパーセンタイル値です。 </td> 
  </tr> 
 </tbody> 
</table>

## 四分位数（表）{#concept_BFD37F0F23A24AD181407142233FA151}

指標の値の四分位数を返します。例えば、四分位数を使用して、最も売上高の多い上位 25 ％の製品を探すことができます。MINV、MEDIAN および MAXV は、クォートがそれぞれ 0（ゼロ）、2、4 と等しい場合、QUARTILE と同じ値を返します。

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> 四分位数を求める指標です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> 四分位数として返す値*を示します。 </td> 
  </tr> 
 </tbody> 
</table>

**quart* = 0 の場合、QUARTILE は最小値を返します。*quart* =1の場合、QUARTILEは第1四分位数（25パーセンタイル）を返します。*quart* =2の場合、QUARTILEは第1四分位数（50パーセンタイル）を返します。*quart* =3の場合、QUARTILEは第1四分位数（75パーセンタイル）を返します。*quart* = 4 の場合、QUARTILE は最大値を返します。

## ラウンド数 {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

指定された値の直近の整数を返します。例えば、製品価格が $569.34 であり、通貨の小数点以下を売上高としてレポートしない場合は、Round(*Revenue*) という数式を使用して、売上高を直近のドル値（$569）に丸めます。$569.51 とレポートされる製品は、直近のドル値（$570）に丸められます。

```
ROUND(metric)
```

| 引数 | 説明 |
|---|---|
| *number* | 丸める指標です。 |

桁数パラメーターのない丸めは、桁数パラメーターが 0 の丸めと同じで、直近の整数に丸めます。桁数パラメーターがある場合、小数の右側が指定された桁数の値が返されます。桁数が負数の場合、小数の左側の指定された桁数が 0 として返されます。

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## 行数 {#concept_0DBF5995881C47CF95F793125F3A0E2B}

指定された列の行の数（ディメンション内でレポートされた一意の要素の数）を返します。「超過したユニーク数」は 1 としてカウントされます。

## 行最大 {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

各行の列の最大値。

## 行の最小 {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

各行の列の最小値。

## 行の合計 {#concept_E9EAB0FC5233498F907E7A078698A98E}

各行の列の合計。

## 平方根（行）{#concept_6460DFA51EC24527A2317970FB76D404}

数の正の平方根を返します。数の平方根は、2 乗してその数になる値です。

```
SQRT(metric)
```

| 引数 | 説明 |
|---|---|
| *number* | 平方根を求める指標です。 |

## 標準偏差（表）{#concept_A383A8BCC6FA42D7B73F7C83997D782A}

データのサンプル母集団に基づいて標準偏差（平方偏差の平方根）を返します。

STDEV の式は次のようになります。

![](assets/std_dev.png)

ここで、x はサンプルの平均値（*metric*）であり、*n* はサンプルサイズです。

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> 引数</b> </td> 
   <td> <b> 説明</b> </td> 
  </tr> 
  <tr> 
   <td> <b><i>metric</i></b> </td> 
   <td> <p> 標準偏差に必要な指標です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 平方偏差（表）{#concept_269751EDC5A34E689112AE16E04A11B0}

データのサンプル母集団に基づいて平方偏差を返します。

VARIANCE の式は次のようになります。

![](assets/variance_eq.png)

ここで、x はサンプルの平均値 MEAN(*metric*) であり、*n* はサンプルサイズです。

```
VARIANCE(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 平方偏差を求める指標です。 |

平方偏差を計算するには、数字の列全体を見ます。まず、すべての数字の平均を求めます。平均を求めたら、各数字に対して次の計算をおこないます。

1. 数字から平均を引きます。

2. 結果を正方形にします。

3. その結果を合計に追加します。

この計算をすべての数字に対して実行し、1 つの合計を求めます。その合計を列内にある数字の個数で除算します。その結果が列の平方偏差です。平方偏差は単一の数字です。ただし、数字の列として表示されます。

例えば、3 つの数字からなる列があるとします。

1

2

3

この列の平均は 2 です。列の平方偏差は（（1-2）²+（2-2）²+（3-2）÷/3=2/3）になります。Ad Hoc Analysis では、次のようになります。

1 2/3

2 2/3

3 2/3
