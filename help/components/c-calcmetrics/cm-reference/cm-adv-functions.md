---
description: これらの関数にアクセスするには、関数ドロップダウンリストの「アドバンスを表示」を選択します。
seo-description: これらの関数にアクセスするには、関数ドロップダウンリストの「アドバンスを表示」を選択します。
seo-title: 高度な関数の参照
title: 高度な関数の参照
uuid: 7d1071b9-1737-4b7c- b318-87907ae5619
translation-type: tm+mt
source-git-commit: ff46935f6ec38c8981e4a1fffdbdc637bdf557db

---


# リファレンス:高度な関数

<!-- 

cm_adv_functions.xml

 -->

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## 表関数と行関数 {#section_8977BE40A47E4ED79EB543A9703A4905}

表関数とは、表のどの行についても出力が同じになる関数です。行関数とは、表の各行で出力が異なる関数です。

## ゼロを含むパラメーターとは {#section_C7A2B05929584C65B308FD372CB8E8E3}

このパラメーターは、計算にゼロを含むかどうかを示します。ゼロは「何もない」ことを意味する場合もあれば、重要な意味を持つ場合もあります。

例えば、売上高の指標がある場合に、ページビュー数の指標をレポートに追加すると、すべてゼロの売上高の行が突然表示されます。売上高の列にある平均値、最小値、四分位数などの計算にこの状況が影響を及ぼすことは好ましくありません。その場合は、ゼロを含むパラメーターを確認します。

一方、対象とする指標が 2 つある場合は、そのうちの 1 つの指標の一部の行がゼロであったという理由で、その指標の平均値が高い、または最小値を持っているとは言えない可能性があります。したがって、この場合は、ゼロを含むパラメーターを確認しません。

## AND {#concept_E14513FE464F4491AD0D4130D4EE621C}

引数の値を返します。値がある特定の値に等しくないことを示すには、NOT を使用します。

>[!NOTE]
>
>0（ゼロ）はFalseを、その他の値はTrueを表します。

```
AND(logical_test1,[logical_test2],...)
```

| 引数 | 説明 |
|---|---|
| *logical_test1* | 必須です。TRUE または FALSE で示される値または式です。 |
| *logical_test2* | (オプション)TRUE または FALSE として求める追加の条件です。 |

## 個別概算カウント（ディメンション）{#concept_000776E4FA66461EBA79910B7558D5D7}

選択したディメンションに関する個別のディメンション項目を概算した数を返します。この関数では、個別カウントを概算する HyperLogLog（HLL）手法を使用しています。  この関数は、値が 95％の確率で実際の値から誤差 5％以内にあることを保証するように設定されています。

```
Approximate Count Distinct (dimension)
```

| 引数 |  |
|---|---|
| *dimension* | 個別の項目数を概算するディメンションです。 |

## 使用例 {#section_424E3FC5092948F0A9D655F6CCBA0312}

個別概算カウント（顧客 ID eVar）は、この関数の一般的な使用例です。

新しい計算指標「概算顧客数」の定義は次のようになります。

![](assets/approx-count-distinct.png)

レポートにおける「概算顧客数」指標の使用方法を以下に示します。

![](assets/approx-customers.png)

## 超過したユニーク数 {#section_9C583858A9F94FF7BA054D1043194BAA}

Count() や RowCount() と同様に、Approximate Count Distinct() も[「超過したユニーク数」制限](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html)の対象です。あるディメンションに関して、特定の月に「超過したユニーク数」制限に達した場合、値は 1 ディメンション項目としてカウントされます。

## カウント関数の比較 {#section_440FB8FB44374459B2C6AE2DA504FC0B}

Approximate Count Distinct() は、Count() 関数および RowCount() 関数を改良したものです。作成した指標を任意のディメンションレポートで使用し、個別のディメンションに関して概算した項目数をレンダリングできます。例としては、モバイルデバイスタイプレポートで使用される顧客 ID 数があります。

この関数は HLL 手法を使用しているので、Count() や RowCount() よりもわずかに精度が低くなります。一方、Count() と RowCount() の数は正確です。

## アークコサイン（行）{#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

指標のアークコサイン（逆コサイン）を返します。アークコサインは、そのコサインが数値である角度です。0（ゼロ）～ pi の範囲のラジアンで角度が返されます。結果をラジアンから度に変換する場合は、その結果に 180/PI( ) を掛けます。

```
ACOS(metric)
```

| 引数 |  |
|---|---|
| *metric* | -1 ～ 1 で求める角度のコサインです。 |

## アークサイン（行）{#concept_90F00DEC46BA47F8A21493647D9668CD}

数のアークサイン（逆サイン）を返します。アークサインは、そのサインが数値である角度です。-pi/2 ～ pi/2 の範囲のラジアンで角度が返されます。アークサインを度で表すには、結果に 180/PI( ) を掛けます。

```
ASIN(metric) 
```

| 引数 |  |
|---|---|
| *metric* | -1 ～ 1 で求める角度のコサインです。 |

## アークタンジェント（行）{#concept_3408520673774A10998E9BD8B909E90C}

数のアークタンジェント（逆タンジェント）を返します。アークタンジェントは、そのタンジェントが数値である角度です。-pi/2 ～ pi/2 の範囲のラジアンで角度が返されます。アークタンジェントを度で表すには、結果に 180/PI( ) を掛けます。

```
ATAN(metric)
```

| 引数 |  |
|---|---|
| *metric* | -1 ～ 1 で求める角度のコサインです。 |

## 指数回帰：予測 Y（行）{#concept_25615693312B4A7AB09A2921083502AD}

「最小二乗」法を使用して、 ) を基に最良の当てはめ線を計算し、指定されている既知の x 値（metric_X）に対する予測 y 値（metric_Y）を算出します。

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

自由度 n のスチューデントの t 分布の値（z スコアが x 未満）の割合を返します。

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

正規分布の値（z スコアが x 未満）の割合を返します。

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## 上限（行）{#concept_A14CDB1E419B4AA18D335E5BA2548346}

指定された値以上の最小の整数を返します。例えば、製品価格が $569.34 であり、通貨の小数点以下を売上高としてレポートしない場合は、CEILING(*Revenue*) という数式を使用して、売上高を直近のドル値（$570）に切り上げます。

```
CEILING(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 丸める指標です。 |

## コサイン（行）{#concept_DD07AA1FB08145DC89B69D704545FD0A}

指定された角度のコサインを返します。角度が度で表されている場合は、角度に PI( )/180 を掛けます。

```
COS(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | コサインを求めるラジアンによる角度です。 |

## 立方根 {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

数の正の立方根を返します。数の立方根は、3 乗してその数になる値です。

```
CBRT(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 立方根を求める指標です。 |

## 累積 {#concept_3D3347797B6344CE88B394C3E39318ED}

最終 N 行の x の合計を返します（ディメンションによって規定されており、文字列ベースのフィールドにハッシュ値を使用します）。

N &lt;= 0 の場合、前のすべての行を使用します。この関数はディメンションによって規定されているので、日付やパスの長さなど、自然順序を持つディメンションでのみ役立ちます。

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## 累加平均 {#concept_ABB650962DC64FD58A79C305282D3E61}

最終 N 行の平均を返します。

N &lt;= 0 の場合、前のすべての行を使用します。この関数はディメンションによって規定されているので、日付やパスの長さなど、自然順序を持つディメンションでのみ役立ちます。

>[!NOTE]
>
>これは、売上高/訪問者数などのレート指標で予想されるものではありません。この指標は、最後のNにわたる売上高を合計し、最後のNを通して訪問者を合計してからそれらを除算する代わりに、レートを平均します。代わりに、次の数式を使用してください。

```
cumul(revenue)/cumul(visitor)
```

## 次と等しい {#concept_A3B97152B5F74E04A97018B35734BEEB}

数字または文字列の値に完全に一致する項目を返します。

## 指数回帰：相関係数（表）{#concept_C18BBFA43C1A499293290DF49566D8D8}

Returns the correlation coefficient, *r*, between two metric columns ( *metric_A* and *metric_B*) for the regression equation .

```
CORREL.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | *metric_Y* とクロス集計する指標です。 |
| *metric_Y* | *metric_X* とクロス集計する指標です。 |

## 指数回帰：切片（表）{#concept_0047206C827841AD936A3BE58EEE1514}

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 指数回帰：傾き（表）{#concept_230991B0371E44308C52853EFA656F04}

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 下限（行）{#concept_D368150EC3684077B284EE471463FC31}

指定された値以下の最大の整数を返します。例えば、製品価格が $569.34 であり、通貨の小数点以下を売上高としてレポートしない場合は、FLOOR(*Revenue*) という数式を使用して、売上高を直近のドル値（$569）に切り捨てます。

```
FLOOR(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 丸める指標です。 |

## 以下の値を超える {#concept_A83734A0C0C14646B76D2CC5E677C644}

入力された値よりも大きい数字を持つ項目を返します。

## 次よりも大きいか等しい {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

入力された値よりも大きいか等しい数字を持つ項目を返します。

## ハイパボリックコサイン（行）{#concept_79DD5681CE9640BDBA3C3F527343CA98}

数のハイパボリックコサインを返します。

```
COSH(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | ハイパボリックコサインを求めるラジアンによる角度です。 |

## ハイパボリックサイン（行）{#concept_96230731600C45E3A4E823FE155ABA85}

数のハイパボリックサインを返します。

```
SINH(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | ハイパボリックサインを求めるラジアンによる角度です。 |

## ハイパボリックタンジェント（行）{#concept_BD249013732F462B9863629D142BCA6A}

数のハイパボリックタンジェントを返します。

```
TANH(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | ハイパボリックタンジェントを求めるラジアンによる角度です。 |

## IF（行）{#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

IF 関数は、指定した条件が TRUE の場合に 1 つの値を返し、その条件が FALSE の場合にもう 1 つの値を返します。

```
IF(logical_test, [value_if_true], [value_if_false])
```

| 引数 | 説明 |
|---|---|
| *logical_test* | 必須です。TRUE または FALSE で示される値または式です。 |
| *[value_if_true]* | *logical_test* 引数の値が TRUE の場合に返す値です（含まれない場合、この引数のデフォルト値は 0 です）。 |
| *[value_if_false]* | *logical_test* 引数の値が FALSE の場合に返す値です（含まれない場合、この引数のデフォルト値は 0 です）。 |

## 未満 {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

入力された値よりも小さい数字を持つ項目を返します。

## 次よりも小さいか等しい {#concept_99D12154DE4848B1B0A6327C4322D288}

入力された値よりも小さいか等しい数字を持つ項目を返します。

## 線形回帰：相関係数 {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b。相関係数を返します。

## 線形回帰：切片 {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b。b を返します。

## 線形回帰：予測 Y {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b。Y を返します。

## 線形回帰：傾き {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b。a を返します。

## 10 を底とする対数（行）{#concept_4C65DF9659164261BE52AA5A95FD6BC1}

数の 10 を底とする対数を返します。

```
LOG10(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 10 を底とする対数を求める正の実数です。 |

## 対数回帰：相関係数（表）{#concept_F3EB35016B754E74BE41766E46FDC246}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. 計算には CORREL 式を使用します。

```
CORREL.LOG(metric_X,metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | *metric_Y* とクロス集計する指標です。 |
| *metric_Y* | *metric_X* とクロス集計する指標です。 |

## 対数回帰：切片（表）{#concept_75A3282EDF54417897063DC26D4FA363}

回帰式 *に対して、2 つの指標列（* metric_X *と* metric_Y *）の間の最小二乗回帰として、切片* b[!DNL Y = a ln(X) + b] を返します。計算には INTERCEPT 式を使用します。

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 対数回帰：予測 Y（行）{#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. 計算には ESTIMATE 式を使用します。

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. [!DNL a] 値は各 x 値に対応し、[!DNL b] は定数値です。

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 対数回帰：傾き（表）{#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. 計算には SLOPE 式を使用します。

```
SLOPE.LOG(metric_A, metric_B)
```

| 引数 | 説明 |
|---|---|
| *metric_A* | 依存データとして指定する指標です。 |
| *metric_B* | 非依存データとして指定する指標です。 |

## 自然対数 {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

数の自然対数を返します。自然対数の底は定数 *e*（2.71828182845904）です。LN は、EXP 関数の逆関数です。

```
LN(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | 自然対数を求める正の実数です。 |

## NOT{#concept_BD954C455A8148A3904A301EC4DC821E}

数が 0 の場合は 1 を返します。別の数の場合は 0 を返します。

```
NOT(logical)
```

| 引数 | 説明 |
|---|---|
| *logical* | 必須です。TRUE または FALSE で示される値または式です。 |

NOT を使用する場合は、式（&lt;、&gt;、=、&lt;&gt; など）が 0 と 1 のどちらの値を返すかを把握しておく必要があります。

## 等しくない {#concept_EC010B7A9D2049099114A382D662FC16}

入力された値の完全一致を含まない項目をすべて返します。

## OR（行）{#concept_AF81A33A376C4849A4C14F3A380639D2}

いずれかの引数が TRUE の場合は TRUE を返します。すべての引数が FALSE の場合は FALSE を返します。

>[!NOTE]
>
>0（ゼロ）はFalseを、その他の値はTrueを表します。

```
OR(logical_test1,[logical_test2],...)
```

| 引数 | 説明 |
|---|---|
| *logical_test1* | 必須です。TRUE または FALSE で示される値または式です。 |
| *logical_test2* | (オプション)TRUE または FALSE として求める追加の条件です。 |

## 円周率 {#concept_41258789660D4A33B5FB86228F12ED9C}

15 桁の精度の定数 PI（3.14159265358979）を返します。

```
PI()
```

[!DNL PI] 関数には引数がありません。

## 累乗回帰：相関係数（表）{#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | *metric_Y* とクロス集計する指標です。 |
| *metric_Y* | *metric_X* とクロス集計する指標です。 |

## 累乗回帰：切片（表）{#concept_7781C85597D64D578E19B212BDD1764F}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 累乗回帰：予測 Y（行）{#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 累乗回帰：傾き（表）{#concept_5B9E71B989234694BEB5EEF29148766C}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 二次回帰：相関係数（表）{#concept_9C9101A456B541E69BA29FCEAC8CD917}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | *metric_Y* とクロス集計する指標です。 |
| *metric_Y* | *metric_X* とクロス集計する指標です。 |

## 二次回帰：切片（表）{#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 二次回帰：予測 Y（行）{#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| 引数 | 説明 |
|---|---|
| *metric_A* | 依存データとして指定する指標です。 |
| *metric_B* | 依存データとして指定する指標です。 |

## 二次回帰：傾き（表）{#concept_0023321DA8E84E6D9BCB06883CA41645}

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 逆数回帰：相関係数（表）{#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

*に対して、2 つの指標列（* metric_X *と* metric_Y *）の間の相関係数* r[!DNL Y = a/X+b] を返します。

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | *metric_Y* とクロス集計する指標です。 |
| *metric_Y* | *metric_X* とクロス集計する指標です。 |

## 逆数回帰：切片（表）{#concept_2DA45B5C69F140EC987649D2C88F19B3}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 逆数回帰：予測 Y（行）{#concept_2CF4B8F417A84FE98050FE488E227DF8}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 逆数回帰：傾き（表）{#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## サイン（行）{#concept_21C8C3AA835947A28B53A4E756A7451E}

指定された角度のサインを返します。角度が度で表されている場合は、角度に PI( )/180 を掛けます。

```
SIN(metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | サインを求めるラジアンによる角度です。 |

## t スコア {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

z スコアのエイリアス。つまり、平均値を標準偏差で割って求める偏差値です。

## t 検定 {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

t スコア col および自由度 n の t 検定（m-tailed）を実行します。

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

ここで、`m` はテール数、`n` は自由度です。これらは数値でなければなりません（全体レポートの場合は、行ごとに変わらない定数でなければなりません）。

`X` は t 検定統計量です。一般的には指標に基づく数式（zscore など）で、すべての行で評価されます。

返される値は、指定された自由度とテール数において検定統計量 x が見られる確率です。

**例：**

1. 外れ値を見つけるには、次の手順を使用します。

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## タンジェント {#concept_C25E00CB17054263AB0460D9EF94A700}

指定された角度のタンジェントを返します。角度が度で表されている場合は、角度に PI( )/180 を掛けます。

```
TAN (metric)
```

| 引数 | 説明 |
|---|---|
| *metric* | タンジェントを求めるラジアンによる角度です。 |

## z スコア（行）{#concept_96BEAC79476C49B899DB7E193A5E7ADD}

正規分布に基づく z スコア（正規スコア）を返します。z スコアは、観測値が平均値から離れている標準偏差の数です。z スコア 0（ゼロ）は、スコアが平均値と同じであることを意味します。z スコアは正と負のどちらにもなり得ます。平均値を上回るか下回るかを標準偏差の数で示します。

z スコアの式は次のようになります。

![](assets/z_score.png)

ここで、[!DNL x] は生のスコア、[!DNL μ] は母集団の平均値、[!DNL σ] は母集団の標準偏差です。

>[!NOTE]
>
>[!DNL μ] （mu）および[!DNL σ] （シグマ）は、指標から自動的に計算されます。

zスコア（指標）

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> <p> 最初のゼロ以外の引数の値を返します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z 検定 {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

z スコア A の Z 検定（n-tailed）を実行します。

現在の行が列に偶然表示される可能性を返します。

>[!NOTE]
>
>値が通常分布すると仮定します。

