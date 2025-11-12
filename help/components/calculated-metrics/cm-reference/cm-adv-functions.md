---
title: 高度な関数
description: 高度な計算指標関数について説明します。
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '5020'
ht-degree: 98%

---

# 高度な関数

[計算指標ビルダー](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)では、統計関数および数学関数を適用できます。この記事では、高度な関数とその定義をアルファベット順に示します。

これらの関数にアクセスするには、コンポーネントパネルの ![効果](/help/assets/icons/Effect.svg) **[!UICONTROL 関数]**&#x200B;リストの下にある「**[!UICONTROL すべて表示]**」を選択します。下にスクロールして、**[!UICONTROL 高度な関数]**&#x200B;のリストを表示します。

## 表関数と行関数

テーブル関数とは、テーブルの行ごとに出力が同じである関数です。 行関数とは、テーブルの行ごとに出力が異なる関数です。

該当する場合および関連する場合、関数には、関数のタイプで注釈が付けられます。[!BADGE テーブル]{type="Neutral"}または[!BADGE 行]{type="Neutral"}

## ゼロを含むパラメーターとは

このパラメーターは、計算にゼロを含むかどうかを示します。ゼロは&#x200B;*何もない*&#x200B;ことを意味する場合もあれば、重要な意味を持つ場合もあります。

例えば、売上高の指標がある場合に、ページビュー数の指標をレポートに追加すると、すべてゼロの売上高の行が突然表示されます。その追加の指標が **[MEAN](cm-functions.md#mean)**（平均値）、**[ROW MINIMUM](cm-functions.md#row-min)**（行の最小値）、**[QUARTILE](cm-functions.md#quartile)**（四分位数）および売上高列にあるその他の計算に影響を与えることは避けるべきです。この場合は、`include-zeros` パラメーターを確認します。

別のシナリオとして、2 つの目標指標があり、一方の指標の平均または最小値が高くなるのは、一部の行がゼロであるためです。その場合、パラメーターにゼロを含めるかどうかを確認しないことを選択できます。


## And {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="And"
>abstract="結合。ゼロに等しくない場合は true、ゼロに等しい場合は false と見なされます。出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

結合。ゼロに等しくない場合は true、ゼロに等しい場合は false と見なされます。出力は 0（false）または 1（true）です。

| 引数 | 説明 |
|---|---|
| logical_test | 少なくとも 1 つのパラメーターが必要ですが、任意の数のパラメーターを指定できます。TRUE または FALSE に評価できる任意の値または式です |


## 個別の概算カウント {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="個別の概算カウント"
>abstract="選択したディメンションのディメンション項目の個別の概算カウントを返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


選択したディメンションのディメンション項目の個別の概算カウントを返します。


| 引数 | 説明 |
|---|---|
| ディメンション | 項目の個別の概算カウントを計算するディメンションです |

### 例

この関数の一般的なユースケースは、顧客の近似数を取得する場合です。



## 逆余弦 {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="逆余弦"
>abstract="指標の逆余弦（余弦の逆数）を返します。逆余弦は、余弦が数値である角度です。返される角度は、0（ゼロ）から pi までの範囲のラジアンで指定されます。結果をラジアンから度に変換する場合は、180/PI() で乗算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE 行]{type="Neutral"} 指標の逆余弦（余弦の逆数）を返します。逆余弦は、余弦が数値である角度です。返される角度は、0（ゼロ）から pi までの範囲のラジアンで指定されます。結果をラジアンから度に変換する場合は、180/PI() で乗算します。


| 引数 | 説明 |
|---|---|
| metric | -1～1 で求める角度の余弦です |



## 逆正弦 {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="逆正弦"
>abstract="数値の逆正弦 （正弦の逆数）を返します。逆正弦は、正弦が数値である角度です。返される角度は、-pi/2 から pi/2 までの範囲のラジアンで指定されます。逆正弦を度で表すには、結果に 180/PI() で乗算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE 行]{type="Neutral"} 数値の逆正弦 （正弦の逆数）を返します。逆正弦は、正弦が数値である角度です。返される角度は、-pi/2 から pi/2 までの範囲のラジアンで指定されます。逆正弦を度で表すには、結果に 180/PI() で乗算します。


| 引数 | 説明 |
|---|---|
| metric | -1～1 で求める角度の正弦です |



## 逆正接 {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="逆正接"
>abstract="数値の逆正接（正接の逆数）を返します。逆正接は、正接が数値である角度です。返される角度は、-pi/2 から pi/2 までの範囲のラジアンで指定されます。逆正接を度で表すには、結果に 180/PI() で乗算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE 行]{type="Neutral"} 数値の逆正接（正接の逆数）を返します。逆正接は、正接が数値である角度です。返される角度は、-pi/2 から pi/2 までの範囲のラジアンで指定されます。逆正接を度で表すには、結果に 180/PI() で乗算します。


| 引数 | 説明 |
|---|---|
| metric | -1～1 で求める角度の正接です |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="自由度 n の student-t 分布を持つランダム変数の z スコアが col より小さくなる確率を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**

自由度 n の student-t 分布を持つランダム変数の z スコアが col より小さくなる確率を返します。

| 引数 | 説明 |
|---|---|
| metric | student t 分布の累積分布関数を求める指標です |
| number | student t 分布の累積分布関数の自由度です |

### 例

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="正規分布を持つランダム変数の z スコアが col より小さくなる確率を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**

正規分布を持つランダム変数の z スコアが col より小さくなる確率を返します。

| 引数 | 説明 |
|---|---|
| metric | 標準正規分布の累積分布関数を求める指標です |

### 例

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## シーリング {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ceil"
>title="シーリング"
>abstract="指定された値以上の最小の整数を返します。例えば、製品価格が $569.34 で、通貨の小数点以下を売上高のレポートに含めない場合は、CEILING(Revenue) という数式を使用して、売上高を最も近いドル値（$570）に切り上げます。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**

[!BADGE 行]{type="Neutral"} 指定された値以上の最小の整数を返します。例えば、製品価格が $569.34 で、通貨の小数点以下を売上高のレポートに含めない場合は、CEILING(Revenue) という数式を使用して、売上高を最も近いドル値（$570）に切り上げます。

| 引数 | 説明 |
|---|---|
| metric | 丸める指標です |


## 信頼性 {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="信頼性"
>abstract="[Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476) の説明に従って、WASKR メソッドを使用して任意の時間で有効な信頼度を計算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

[Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476) の説明に従って、WASKR メソッドを使用して任意の時間で有効な信頼度を計算します。

信頼性は、特定のバリアントがコントロールバリアントと同じであるという証拠がどの程度あるかを示す確率測度です。信頼性が高いほど、コントロールバリアントおよびコントロールバリアント以外のパフォーマンスが等しいという仮定に対する証拠が少ないことを示します。

| 引数 | 説明 |
| --- | --- |
| normalizing-container | テストが実行される基準（人物、セッションまたはイベント）。 |
| success-metric | ユーザーがバリアントと比較する指標。 |
| control | 実験におけるその他すべてのバリアントと比較されるバリアント。コントロールバリアントディメンション項目の名前を入力します。 |
| significance-threshold | この関数のしきい値は、デフォルトの 95%に設定されています。 |


## 信頼（下限） {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lower-individual-confidence-sequence"
>title="信頼（下限）"
>abstract="[Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476) の説明に従って、WASKR メソッドを使用して任意の時間で有効な信頼&#x200B;**下限**&#x200B;を計算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

[Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476) の説明に従って、WASKR メソッドを使用して任意の時間で有効な信頼&#x200B;**下限**&#x200B;を計算します。

信頼性は、特定のバリアントがコントロールバリアントと同じであるという証拠がどの程度あるかを示す確率測度です。信頼性が高いほど、コントロールバリアントおよびコントロールバリアント以外のパフォーマンスが等しいという仮定に対する証拠が少ないことを示します。

| 引数 | 説明 |
| --- | --- |
| normalizing-container | テストが実行される基準（人物、セッションまたはイベント）。 |
| success-metric | ユーザーがバリアントと比較する指標。 |
| control | 実験におけるその他すべてのバリアントと比較されるバリアント。コントロールバリアントディメンション項目の名前を入力します。 |
| significance-threshold | この関数のしきい値は、デフォルトの 95%に設定されています。 |

## 信頼（上限） {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-upper-individual-confidence-sequence"
>title="信頼（上限）"
>abstract="[Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476) の説明に従って、WASKR メソッドを使用して任意の時間で有効な信頼&#x200B;**上限**&#x200B;を計算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

[Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476) の説明に従って、WASKR メソッドを使用して任意の時間で有効な信頼&#x200B;**上限**&#x200B;を計算します。

信頼性は、特定のバリアントがコントロールバリアントと同じであるという証拠がどの程度あるかを示す確率測度です。信頼性が高いほど、コントロールバリアントおよびコントロールバリアント以外のパフォーマンスが等しいという仮定に対する証拠が少ないことを示します。

| 引数 | 説明 |
| --- | --- |
| normalizing-container | テストが実行される基準（人物、セッションまたはイベント）。 |
| success-metric | ユーザーがバリアントと比較する指標。 |
| control | 実験におけるその他すべてのバリアントと比較されるバリアント。コントロールバリアントディメンション項目の名前を入力します。 |
| significance-threshold | この関数のしきい値は、デフォルトの 95%に設定されています。 |


## 余弦 {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="余弦"
>abstract="指定された角度の余弦を返します。 角度の単位が「度」の場合は、角度に PI()/180 で乗算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE 行]{type="Neutral"} 指定された角度の余弦を返します。角度の単位が「度」の場合は、角度に PI()/180 で乗算します。

| 引数 | 説明 |
|---|---|
| metric | 余弦を求めるラジアンの角度 |


## 立方根 {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="立方根"
>abstract="数値の正の立方根を返します。数値の立方根は、その数値を 1/3 乗した値です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


数値の正の立方根を返します。数値の立方根は、その数値を 1/3 乗した値です。


| 引数 | 説明 |
|---|---|
| metric | 立方根の計算を求める指標 |



## 累積 {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="累積"
>abstract="列 x の最後 n 個の要素の合計を返します。n > 0 の場合は、最後 n 個の要素または x を合計します。n &lt; 0 の場合は、前の要素を合計します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

列 x の最後 n 個の要素の合計を返します。n > 0 の場合は、最後 n 個の要素または x を合計します。n &lt; 0 の場合は、前の要素を合計します。

| 引数 | 説明 |
| --- | --- |
| number | 合計を返す最終 N 行の値です。N &lt;= 0 の場合、前のすべての行を使用します。 |
| metric | 累積合計を求める指標です。 |

### 例

| 日付 | 売上高 | CUMULATIVE(0, Revenue) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| 5月 | $500 | $500 | $500 |
| 6月 | $200 | $700 | $700 |
| 7月 | $400 | $1100 | $600 |


## 累積（平均） {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="累積（平均）"
>abstract="列 x の最後の n 要素の平均を返します。n > 0 の場合は、最後の n 要素または x を合計します。n &lt; 0 の場合は、前の要素を合計します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

列 x の最後の n 要素の平均を返します。n > 0 の場合は、最後の n 要素または x を合計します。n &lt; 0 の場合は、前の要素を合計します。

| 引数 | 説明 |
| --- | --- |
| number | 平均を返す最終 N 行の値です。N &lt;= 0 の場合、前のすべての行を使用します。 |
| metric | 累積平均を求める指標です。 |

>[!NOTE]
>
>この関数は、ユーザーごとの売上高などのレート指標では機能しません。この関数は、最後の N の売上高を合計し、最後の N のユーザーを合計して除算するのではなく、レートを平均します。<br/>代わりに、[**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![除算](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative) を使用します。
>


## 等号 {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="等号"
>abstract="次と等しい。出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

次と等しい。出力は 0（false）または 1（true）です。


| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 = Metric 2`


## 指数回帰：相関係数 {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="指数回帰：相関係数"
>abstract="指数回帰：Y = a exp(X) + b。相関係数を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE テーブル]{type="Neutral"} 指数回帰：Y = a exp(X) + b。相関係数を返します。


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y とクロス集計する指標です |
| metric_Y | metric_X とクロス集計する指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |

## 指数回帰：予測 Y {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="指数回帰：予測 Y"
>abstract="指数回帰：Y = a exp(X) + b。Y を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE 行]{type="Neutral"} 指数回帰：Y = a exp(X) + b。Y を返します。


| 引数 | 説明 |
|---|---|
| metric_X | 非依存データとして指定する指標です。 |
| metric_Y | 依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 指数回帰：切片 {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="指数回帰：切片"
>abstract="指数回帰：Y = a exp(X) + b。b を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE テーブル]{type="Neutral"} 指数回帰：Y = a exp(X) + b。b を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 指数回帰：傾き {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="指数回帰：傾き"
>abstract="指数回帰：Y = a exp(X) + b。a を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE テーブル]{type="Neutral"} 指数回帰：Y = a exp(X) + b。a を返します。


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 下限 {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="下限"
>abstract="指定された値以下の最大の整数を返します。例えば、製品価格が $569.34 であり、通貨の小数点以下を売上高としてレポートしない場合は、FLOOR(Revenue) という数式を使用して、売上高を直近のドル値（$569）に切り下げます。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"} 指定された値以下の最大の整数を返します。例えば、製品価格が $569.34 であり、通貨の小数点以下を売上高としてレポートしない場合は、FLOOR(Revenue) という数式を使用して、売上高を直近のドル値（$569）に切り下げます。

| 引数 | 説明 |
|---|---|
| metric | 四捨五入する指標です。 |


## 次より大きい {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="次より大きい"
>abstract="出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**

出力は 0（false）または 1（true）です。

| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 > Metric 2`


## 次よりも大きいか等しい {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="次よりも大きいか等しい"
>abstract="次よりも大きいか等しい。出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**

次よりも大きいか等しい。出力は 0（false）または 1（true）です。

| 引数 | 説明 |
|---|---|
| metric_X |  |
| metric_Y |  |

### 例

`Metric 1 >= Metric 2`



## 双曲線余弦 {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="双曲線余弦"
>abstract="数値の双曲線余弦を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE 行]{type="Neutral"} 数値の双曲線余弦を返します。


| 引数 | 説明 |
|---|---|
| metric | 双曲線余弦を求めるラジアンの角度です |



## 双曲線正弦 {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="双曲線正弦"
>abstract="数値の双曲線正弦を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**

[!BADGE 行]{type="Neutral"} 数値の双曲線正弦を返します。

| 引数 | 説明 |
|---|---|
| metric | 双曲線正弦を求めるラジアンの角度です |


## 双曲線正接 {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="双曲線正接"
>abstract="数値の双曲線正接を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**

[!BADGE 行]{type="Neutral"} 数値の双曲線正接を返します。

| 引数 | 説明 |
|---|---|
| metric | 双曲線正接を求めるラジアンの角度です |


## If {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="If"
>abstract="条件パラメーターの値がゼロ以外（true）の場合、結果は value_if_true パラメーターの値になります。 それ以外の場合は、value_if_false パラメーターの値になります。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE 行]{type="Neutral"} 条件パラメーターの値がゼロ以外（true）の場合、結果は value_if_true パラメーターの値になります。それ以外の場合は、value_if_false パラメーターの値になります。


| 引数 | 説明 |
|---|---|
| logical_test | 必須。TRUE または FALSE に評価できる任意の値または式です |
| value_if_true | logical_test 引数が TRUE に評価された場合に返される値です（含まれない場合、この引数のデフォルト値は 0 です）。 |
| value_if_false | logical_test 引数の値が FALSE の場合に返す値です (含まれない場合、この引数のデフォルト値は 0 です)。 |


## 次の値未満 {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="次の値未満"
>abstract="出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

出力は 0（false）または 1（true）です。

| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 < Metric 2`


## 次よりも小さいか等しい {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="次よりも小さいか等しい"
>abstract="次よりも小さいか等しい。出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

次よりも小さいか等しい。出力は 0（false）または 1（true）です。

| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 <= Metric 2`



## 上昇率（#lift）

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="上昇率"
>abstract="制御値と比較した比率の上昇率。"

<!-- markdownlint-enable MD034 -->

| 引数 | 説明 |
| --- | --- |
| normalizing-container | テストが実行される基準（人物、セッションまたはイベント）。 |
| success-metric | ユーザーがバリアントと比較する指標。 |
| control | 実験におけるその他すべてのバリアントと比較されるバリアント。コントロールバリアントディメンション項目の名前を入力します。 |



## 線形回帰：相関係数 {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="線形回帰：相関係数"
>abstract="線形回帰：Y = a X + b。相関係数を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE テーブル]{type="Neutral"} 線形回帰：Y = a X + b。相関係数を返します。


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y とクロス集計する指標です |
| metric_Y | metric_X とクロス集計する指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 線形回帰：切片 {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="線形回帰：切片"
>abstract="線形回帰：Y = a X + b。b を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE テーブル]{type="Neutral"} 線形回帰：Y = a X + b。b を返します。


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 線形回帰：予測 Y {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="線形回帰：予測 Y"
>abstract="線形回帰：Y = a X + b。Y を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE 行]{type="Neutral"} 線形回帰：Y = a X + b。Y を返します。


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 線形回帰：傾き {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="線形回帰：傾き"
>abstract="線形回帰：Y = a X + b。a を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 線形回帰：Y = a X + b。a を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 対数ベース 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="対数ベース 10"
>abstract="数値のベース 10 の対数を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE 行]{type="Neutral"} 数値のベース 10 の対数を返します。


| 引数 | 説明 |
|---|---|
| metric | 基数 10 の対数を求める正の実数です。 |


## 対数回帰：相関係数 {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="対数回帰：相関係数"
>abstract="対数回帰：Y = a ln(X) + b。相関係数を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 対数回帰：Y = a ln(X) + b。相関係数を返します。

| 引数 | 説明 |
|---|---|
| metric_X | metric_Y とクロス集計する指標です |
| metric_Y | metric_X とクロス集計する指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 対数回帰：切片 {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="対数回帰：切片"
>abstract="対数回帰：Y = a ln(X) + b。b を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 対数回帰：Y = a ln(X) + b。b を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 対数回帰：予測 Y {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="対数回帰：予測 Y"
>abstract="対数回帰：Y = a ln(X) + b。Y を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"} 対数回帰：Y = a ln(X) + b。Y を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 対数回帰：傾き {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="対数回帰：傾き"
>abstract="対数回帰：Y = a ln(X) + b。a を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 対数回帰：Y = a ln(X) + b。a を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 自然対数 {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="自然対数"
>abstract="値の自然対数を返します。自然対数は、定数 e（2.71828182845904）に基づきます。LN は EXP 関数の逆関数です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**

値の自然対数を返します。自然対数は、定数 e（2.71828182845904）に基づきます。LN は EXP 関数の逆関数です。

| 引数 | 説明 |
|---|---|
| metric | 自然対数を求める正の実数です |



## Not {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="Not"
>abstract="ブール値としての否定。出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**

ブール値としての否定。出力は 0（false）または 1（true）です。

| 引数 | 説明 |
|---|---|
| logical | 必須。TRUE または FALSE で示される値または式です |



## 次と等しくない {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="次と等しくない"
>abstract="次と等しくない。出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


次と等しくない。出力は 0（false）または 1（true）です。


| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 != Metric 2`


## または {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="または"
>abstract="分離。ゼロに等しくない場合は true、ゼロに等しい場合は false と見なされます。出力は 0（false）または 1（true）です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE 行]{type="Neutral"} 分離。ゼロに等しくない場合は true、ゼロに等しい場合は false と見なされます。出力は 0（false）または 1（true）です。


| 引数 | 説明 |
|---|---|
| logical_test | 少なくとも 1 つのパラメーターが必要ですが、任意の数のパラメーターを指定できます。TRUE または FALSE に評価できる任意の値または式です |


>[!NOTE]
>
>0（ゼロ）は False を表し、それ以外の値は True を表します。


## 円周率 {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="円周率"
>abstract="円周率を返します。円周率：3.14159.."

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

円周率を返します。円周率：3.14159..


## 累乗回帰：相関係数 {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="累乗回帰：相関係数"
>abstract="累乗回帰：Y = b X ^ a。相関係数を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 累乗回帰：Y = b X ^ a。相関係数を返します。

| 引数 | 説明 |
|---|---|
| metric_X | metric_Y とクロス集計する指標です |
| metric_Y | metric_X とクロス集計する指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 累乗回帰：切片 {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="累乗回帰：切片"
>abstract="累乗回帰：Y = b X ^ a。b を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE テーブル]{type="Neutral"} 累乗回帰：Y = b X ^ a。b を返します。


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 累乗回帰：予測 Y {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="累乗回帰：予測 Y"
>abstract="累乗回帰：Y = b X ^ a。Y を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"} 累乗回帰：Y = b X ^ a。Y を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 累乗回帰：傾き {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="累乗回帰：傾き"
>abstract="累乗回帰：Y = b X ^ a。a を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 累乗回帰：Y = b X ^ a。a を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 二次回帰：相関係数 {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="二次回帰：相関係数"
>abstract="二次回帰：Y = (a + bX) ^ 2、相関係数を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 二次回帰：Y = (a + bX) ^ 2、相関係数を返します。

| 引数 | 説明 |
|---|---|
| metric_X | metric_Y とクロス集計する指標です |
| metric_Y | metric_X とクロス集計する指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |

## 二次回帰：切片 {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="二次回帰：切片"
>abstract="二次回帰：Y = (a + bX) ^ 2、a を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 二次回帰：Y = (a + bX) ^ 2、a を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 二次回帰：予測 Y {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="二次回帰：予測 Y"
>abstract="二次回帰：Y = (a + bX) ^ 2、Y を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"} 二次回帰：Y = (a + bX) ^ 2、Y を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 二次回帰：傾き {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="二次回帰：傾き"
>abstract="二次回帰：Y = (a + bX) ^ 2、b を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 二次回帰：Y = (a + bX) ^ 2、b を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 逆数回帰：相関係数 {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="逆数回帰：相関係数"
>abstract="逆数回帰：Y = a + b X ^ -1。相関係数を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 逆数回帰：Y = a + b X ^ -1。相関係数を返します。

| 引数 | 説明 |
|---|---|
| metric_X | metric_Y とクロス集計する指標です |
| metric_Y | metric_X とクロス集計する指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 逆数回帰：切片 {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="逆数回帰：切片"
>abstract="逆数回帰：Y = a + b X ^ -1。a を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 逆数回帰：Y = a + b X ^ -1。a を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 逆数回帰：予測 Y {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="逆数回帰：予測 Y"
>abstract="逆数回帰：Y = a + b X ^ -1。Y を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"} 逆数回帰：Y = a + b X ^ -1。Y を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 逆数回帰：傾き {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="逆数回帰：傾き"
>abstract="逆数回帰：Y = a + b X ^ -1。b を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 逆数回帰：Y = a + b X ^ -1。b を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標です |
| metric_Y | 非依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |




## 正弦 {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="正弦"
>abstract="指定された角度の正弦を返します。角度の単位が「度」の場合は、角度に PI()/180 で乗算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE 行]{type="Neutral"} 指定された角度の正弦を返します。角度の単位が「度」の場合は、角度に PI()/180 で乗算します。


| 引数 | 説明 |
|---|---|
| metric | 正弦を求めるラジアンの角度です |




## t スコア {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="t スコア"
>abstract="[平均値](cm-functions.md#mean)を標準偏差で割って求める偏差値です。[z スコア](#z-score)のエイリアス。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

[平均値](cm-functions.md#mean)を標準偏差で割って求める偏差値です。[z スコア](#z-score)のエイリアス。

| 引数 | 説明 |
|---|---|
| metric | t スコアを求める指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |


## t 検定 {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="t 検定"
>abstract="t スコア x および自由度 n の t 検定（m-tailed）を実行します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**

t スコア x および自由度 n の t 検定（m-tailed）を実行します。

| 引数 | 説明 |
|---|---|
| metric | t 検定を行う指標です |
| degrees | 自由度です |
| すそ | t 検定を実行するために使用されるすその長さです。 |

### 詳細

署名は T-TEST(metric, degrees, tails) です。その下には、単に ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)** を呼び出します。この関数は、***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)** を実行する **[Z-TEST](#z-test)** 関数に類似しています。

- ***m*** はすその数です。
- ***n*** は自由度で、レポート全体に対して一定の数値にする必要があります。つまり、行単位で変更されません。
- ***X*** は t 検定統計量です。一般的には指標に基づく数式（**[Z-SCORE](#z-score)** など）で、すべての行で評価されます。

返される値は、指定された自由度とテール数において検定統計量 x が見られる確率です。

### 例

1. 次の関数を使用して異常値を見つけます。

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. この関数に **[IF](#if)** を組み合わせて、極度に高いまたは低いバウンス率を無視し、その他すべてへの訪問回数をカウントします。

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## 正接 {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="正接"
>abstract="指定された角度の正接を返します。 角度の単位が「度」の場合は、角度に PI()/180 で乗算します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**

指定された角度の正接を返します。 角度の単位が「度」の場合は、角度に PI()/180 で乗算します。

| 引数 | 説明 |
|---|---|
| metric | 正接を求めるラジアンの角度です |



## z スコア {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="z スコア"
>abstract="平均値を標準偏差で割って求める偏差値です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE 行]{type="Neutral"} 平均値を標準偏差で割って求める偏差値です。

| 引数 | 説明 |
|---|---|
| metric | z スコアを求める指標です |
| include_zeros | 計算にゼロ値を含めるかどうか |

z スコア 0（ゼロ）は、スコアが平均値と同じであることを意味します。Z スコアは正または負の値となり、平均より上または下であるかどうか、および標準偏差の数を示します。

Z スコアの計算式は次のとおりです。

![](assets/z_score.png)

ここで、***[!DNL x]*** は生のスコア、***[!DNL μ]*** は母集団の平均値、***[!DNL σ]*** は母集団の標準偏差です。

>[!NOTE]
>
>***[!DNL μ]***（ミュー）および ***[!DNL σ]***（シグマ）は、指標から自動的に計算されます。



## Z 検定 {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="Z 検定"
>abstract="z スコア x の z 検定（n-tailed）を実行します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

z スコア x の z 検定（n-tailed）を実行します。

| 引数 | 説明 |
|---|---|
| metric | z 検定を行う指標です |
| すそ | z 検定を行うために使用するすその長さです |

>[!NOTE]
>
>値が正規分布されると仮定します。




<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts. It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->