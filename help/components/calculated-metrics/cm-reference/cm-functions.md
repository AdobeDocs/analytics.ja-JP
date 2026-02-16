---
title: 基本的な関数
description: 基本的な計算指標関数について説明します。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: b8fae74ade75473f3d3d8d43598dfb16170b209f
workflow-type: tm+mt
source-wordcount: '3600'
ht-degree: 49%

---

# 基本関数


[計算指標ビルダー](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)では、統計関数および数学関数を適用できます。この記事では、関数とその定義のアルファベット順のリストについて説明します。

>[!NOTE]
>
>[!DNL metric] が関数の引数として特定されている場合は、指標の他の式も許可されます。例えば、[COLUMN MAXIMUM(metrics)](#column-maximum) を [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum) としてもかまいません。



## 表関数と行関数

テーブル関数とは、テーブルの行ごとに出力が同じである関数です。 行関数とは、テーブルの行ごとに出力が異なる関数です。

該当する場合および関連する場合、関数には、関数のタイプで注釈が付けられます。[!BADGE テーブル]{type="Neutral"}または[!BADGE 行]{type="Neutral"}

## ゼロを含むパラメーターとは

このパラメーターは、計算にゼロを含むかどうかを示します。ゼロは&#x200B;*何もない*&#x200B;ことを意味する場合もあれば、重要な意味を持つ場合もあります。

例えば、売上高の指標がある場合に、ページビュー数の指標をレポートに追加すると、すべてゼロの売上高の行が突然表示されます。その追加の指標が **[MEAN](cm-functions.md#mean)**（平均値）、**[ROW MINIMUM](cm-functions.md#row-min)**（行の最小値）、**[QUARTILE](cm-functions.md#quartile)**（四分位数）および売上高列にあるその他の計算に影響を与えることは避けるべきです。この場合は、`include-zeros` パラメーターを確認します。

別のシナリオとして、2 つの目標指標があり、一方の指標の平均または最小値が高くなるのは、一部の行がゼロであるためです。その場合、パラメーターにゼロを含めるかどうかを確認しないことを選択できます。



## 絶対値 {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="絶対値"
>abstract="数値の絶対値を返します。数値の絶対値は、正の値を持つ数値です。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE 行]{type="Neutral"} 数値の絶対値を返します。数値の絶対値は、正の値を持つ数値です。

| 引数 | 説明 |
|---|---|
| 指標 | 絶対値を求める指標です。 |

**ユースケース**：売上高の差分や割合の変更など、負の値を生じる可能性のある指標を分析する際に、すべての結果が正であることを確認します。 これは、方向に関係なく、変化の大きさに焦点を合わせるのに役立ちます。

**計算指標ビルダー**：指標または式を **絶対値** 関数に含めます。例：**絶対値** （現在の売上高 – 以前の売上高）。 これにより、負の差が正の値に変換されます。

>[!TIP]
>
>これは、パフォーマンスの増加または減少に関係なく、2 つの期間またはセグメント間の絶対差異を測定するために使用します。
>

## 列の最大値 {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="列の最大値"
>abstract="指標列の一連のディメンション要素の中の最大値を返します。MAXV は、ディメンション要素をまたいで、1 つの列（指標）内を垂直方向に評価します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

指標列の一連のディメンション要素の中の最大値を返します。MAXV は、ディメンション要素をまたいで、1 つの列（指標）内を垂直方向に評価します。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**：訪問数が最も多い日や、売上高が最も高い製品など、分類内の最も高い値を特定します。 これは、カテゴリ間のピーク時のパフォーマンスを強調するのに役立ちます。

**計算指標ビルダー**:**日** または *製品* で分類する場合の *売上高* または *訪問回数* などの指標に *列の最大値* を適用します。 この関数は、各行のその列の最大値を返します。

>[!TIP]
>
>[IF](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if) （**Revenue** = *Column Maximum&#x200B;**（Revenue*）, 1, 0）などの &#x200B;** IF** ステートメントを使用して、分類で最もパフォーマンスの高い項目をハイライト表示します。
>

## 列の最小値 {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="列の最小値"
>abstract="指標列の一連のディメンション要素の中の最小値を返します。MINV は、ディメンション要素をまたいで、1 つの列（指標）内を垂直方向に評価します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

指標列の一連のディメンション要素の中の最小値を返します。MINV は、ディメンション要素をまたいで、1 つの列（指標）内を垂直方向に評価します。

| 引数 | 説明 |
|---|---|
| 指標 | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定できます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**：コンバージョン数が最も少ないキャンペーンや売上高が最も少ない日など、分類内のパフォーマンスが最も低い値を特定します。 これにより、パフォーマンスの低いセグメントをすばやく表示できます。

**計算指標ビルダー**:**キャンペーン** または *日* で分類する際に、*売上高* または *コンバージョン率* などの指標に *列の最小値* を適用します。 この関数は、各行のその列の最小値を返します。

>[!TIP]
>
>[IF](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if) （**収益** = *列最小&#x200B;**（収益*）、1、0）などの &#x200B;** IF** ステートメントを使用して、分類でパフォーマンスの低い項目をハイライト表示します。
>


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

**ユースケース**：すべての製品の合計売上高や全日の合計訪問回数など、分類内のすべての値の合計を計算します。 これは、個々の行の値と比較するために全体的な合計が必要な場合に役立ちます。

**計算指標ビルダー**:**製品** または *日* で分類しながら、*売上高* または *訪問回数* などの指標に *列合計* を適用します。 この関数は、各行のその列に含まれるすべての値の合計を返します。

>[!TIP]
>
>株式またはパフォーマンス全体に対する割合を計算するために、全体の合計に対する参照が必要な場合に使用します。
>


## カウント {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="カウント"
>abstract="1 つの列内の指標のゼロ以外の値の数（カウント）（ディメンション内でレポートされた一意の要素の数）を返します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE テーブル]{type="Neutral"} 1 つの列内の指標のゼロ以外の値の数（カウント）（ディメンション内でレポートされた一意の要素の数）を返します。

| 引数 | 説明 |
|---|---|
| 指標 | カウントする指標です。 |

**ユースケース**：日付範囲の日数や分類の製品数など、計算に含まれるデータポイント数をカウントします。 これは、集計値に貢献するアイテムの数を把握する必要がある場合に役立ちます。

**計算指標ビルダー**:**カウント** を *訪問回数* や *売上高* などの指標に適用して、現在の分類または日付範囲に含まれる行（またはデータポイント）の合計数を返します。

>[!TIP]
>
>**列の合計** と共に使用して、平均を手動で計算します（例：**列の合計** （*売上高*）/**カウント** （売上高））。
>

## 指数 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="指数"
>abstract="指定された数値の累乗した e を返します。定数 e は、自然対数のベースである 2.71828182845904 に等しくなります。EXPONENT（指数）は LN（数の自然対数）の逆関数です。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE 行]{type="Neutral"} 指定された数値の累乗した e を返します。定数 e は、自然対数のベースである 2.71828182845904 に等しくなります。EXPONENT（指数）は LN（数の自然対数）の逆関数です。

| 引数 | 説明 |
|---|---|
| 指標 | 底 e に適用される指数です。 |

**ユースケース**:*e* を指定された数値または指標の累乗に上げます。 これは、成長の傾向をモデリングする場合や、指標を指数関数的に拡大縮小する場合に役立ちます。

**計算指標ビルダー内**：指標で **指数** を使用します。 例：**Exponent** （*Visits*）は、*e* を *Visits* 指標の累乗に上げます。

>[!TIP]
>
>**対数** と組み合わせて高度なモデリングを行ったり、成長パターンを比較する際に変数の高いデータをスムーズに処理したりできます。
>


## 平均 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="平均"
>abstract="1 つの列の指標の算術平均（平均値）を返します。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 1 つの列の指標の算術平均（平均値）を返します。

| 引数 | 説明 |
|---|---|
| 指標 | 平均を求める指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**:1 日あたりの平均売上高やキャンペーンあたりの平均訪問回数など、一連の値の算術平均を計算します。 これは、データセット内の個々の値を比較するためのベースラインを確立するのに役立ちます。

**計算指標ビルダー**:**売上高** または *訪問回数* などの指標に *平均* を適用して、選択した分類または日付範囲のすべてのデータポイントの平均値を返します。

>[!TIP]
>
>を使用して全体的なパフォーマンストレンドを把握するか、**標準偏差** と組み合わせて平均に関する一貫性を測定します。
>

## 中央値 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="中央値"
>abstract="1 つの列の指標の中央値を返します。中央値は、一連の数の中央にある数値です。つまり、数の半分は中央値よりも大きいか等しい値であり、残りの半分は中央値よりも小さいか等しい値です。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 1 つの列の指標の中央値を返します。中央値は、一連の数の中央にある数値です。つまり、数の半分は中央値よりも大きいか等しい値であり、残りの半分は中央値よりも小さいか等しい値です。

| 引数 | 説明 |
|---|---|
| 指標 | 中央値を求める指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**:1 日の売上高の中央値や 1 訪問あたりのページビューの中央値など、一連のデータの中の中央値を特定します。 これは、異常値の影響を軽減し、データの中心傾向を確認する場合に役立ちます。

**計算指標ビルダー**：収益やページビューなどの指標に中央値を適用し、選択した分類または日付範囲のすべてのデータポイントにわたる中間値を返します。

>[!TIP]
>
>データに、平均をゆがめる可能性のある極端な高値や安値が含まれる場合は、**平均** の代わりにを使用します。
>


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

**ユースケース**：ある数値を別の数値で割った後の残りを返します。 これは、n 日目ごと、またはシーケンス内のキャンペーンを識別するなど、循環パターンや繰り返しパターンに役立ちます。

**計算指標ビルダーで**:2 つの数値入力で **モジュロ** を使用します。 例：**Modulo** （*Day Number*, 7）は、日の数値を 7 で割った後の剰余を返します。これにより、データを週でグループ化するのに役立ちます。

>[!TIP]
>
>条件付きロジックと組み合わせて、繰り返し間隔をハイライト表示したり、繰り返しサイクルに基づいてデータをセグメント化したりします。
>

### その他の例

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

[!BADGE テーブル]{type="Neutral"} 0～100 の値である、n 番目のパーセンタイルを返します。n &lt; 0 の場合、関数は 0 を使用します。n > 100 の場合、関数は 100 を返します。

| 引数 | 説明 |
|---|---|
| 指標 | 0 ～ 100（0 と 100 を含む）の範囲のパーセンタイル値です。 |
| k | 相対的な値を定義する指標列です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**：毎日の売上高またはページビューの 90 パーセンタイルなど、特定のデータポイントの割合が低下する値を特定します。 これにより、分布を測定し、パフォーマンスの高い異常値を検出できます。

**計算指標ビルダー**:**パーセンタイル** を *売上高* または *訪問回数* などの指標に適用し、目的のパーセンタイル値（例：**パーセンタイル** （*売上高*、90））を指定します。 その結果、データポイントの 90% が低下するしきい値が示されます。

>[!TIP]
>
>パフォーマンスベンチマークの設定や、パフォーマンスの高い日、キャンペーン、製品のフィルタリングに使用します。
>

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

**ユースケース**：値の二乗や指数の重み付けなど、ある数値または指標を別の数値の累乗に増やします。 これは、成長をモデリングしたり、値をスケーリングしたり、高度な数学的変換を実行したりする場合に役立ちます。

**計算指標ビルダー内**:2 つの数値または指標の間で **累乗演算子** を使用します。 例：*Revenue* ^ 2 は、*Revenue* 値を 2 乗します。

>[!TIP]
>
>**Exponent** 関数に似ていますが、数学演算子として表現され、計算指標内の式をよりコンパクトにすることができます。
>

## 四分位数 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="四分位数"
>abstract="指標の値の四分位数を返します。例えば、四分位数を使用して、最も売上高の多い上位 25 ％の製品を探すことができます。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} 指標の値の四分位数を返します。例えば、四分位数を使用して、最も売上高の多い上位 25 ％の製品を探すことができます。[COLUMN MINIMUM](#column-minimum)、[MEDIAN](#median)、および [COLUMN MAXIMUM](#column-maximum) は、四分位数がそれぞれ `0`（ゼロ）、`2`、`4` に等しい場合、[QUARTILE](#quartile) と同じ値を返します。

| 引数 | 説明 |
|---|---|
| 指標 | 四分位数値を求める指標です。 |
| 四分位数 | 四分位数として返す値を示します。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**：データセットを 4 つの等しい部分に分割して、収益または訪問数による上位 25% の日の特定など、値の配分方法を理解します。 これにより、パフォーマンスをランク付けされたグループにセグメント化して、より詳細に比較できます。

**計算指標ビルダー**:**四分位数** を *売上高* や *訪問回数* などの指標に適用し、返す四分位数を指定します（例：**四分位数** （*売上高*、3）。これにより、3 番目の四分位数のしきい値、つまり上位 25% を見つけることができます）。

>[!TIP]
>
>を使用して、パフォーマンスの低い層、中程度の層、高い層のキャンペーンや製品に値をグループ化します。
>

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
| metric | 四捨五入する指標です。 |
| 数 | 小数点の右側に返す桁数。（負の数が小数点の左側に 0 を返す場合）。 |

**ユースケース**：指定された小数点以下の桁数に丸めることで、数値結果を簡略化します。 これは、よりクリーンなビジュアライゼーションを作成したり、計算指標をレポートで読みやすくしたりするのに役立ちます。

**計算指標ビルダー**：指標または式に **丸め** を適用し、小数点以下の桁数を指定します。 例：**Round** （*Conversion Rate*, 2）は、値を小数点以下 2 桁に丸めます。

>[!TIP]
>
>特に割合や通貨の値を表示する場合に、を使用してレポート全体で指標の書式を標準化します。
>

### その他の例

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

**ユースケース**：レポートに含まれる日数、キャンペーン数、製品数など、分類またはデータセットで返される行の合計数をカウントします。 これは、分析に貢献する項目の数を理解するのに役立ちます。

**計算指標ビルダー**:**行数** を適用して、現在の分類またはセグメントの行の合計数を返します。 例えば、*Revenue* を *Product* で表示すると、**Row Count** は表示された製品の数を返します。

>[!TIP]
>
>**列の合計** などの他の関数と共に使用して、平均を手動で計算します（例：**列の合計** （*売上高*）/**行の数** （））。
>

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

**ユースケース**：特定の日またはセグメントに最大の値を持つ指標（例：*売上高*、*注文件数*、*訪問回数*）の決定など、1 行のすべての指標の中で最も高い値を特定します。 これは、データの各行でどの指標リードをハイライト表示するのに役立ちます。

**計算指標ビルダー**：計算指標に複数の指標が含まれる場合に **行の最大値** を適用します。 例：**Row Maximum** （*Revenue*, *Orders*, *Visits*）は、各行のこれらの指標の中で最大値を返します。

>[!TIP]
>
>を使用して、関連指標を並べて比較し、各行内でパフォーマンスに最も貢献している指標を特定します。
>

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

**ユースケース**：特定の日またはセグメントに最小値を持つ指標（例：*売上高*、*注文件数*、*訪問回数*）を検索するなど、1 行のすべての指標の中で最小値を特定します。 これにより、データの各行で最もパフォーマンスの低い指標を見つけることができます。

**計算指標ビルダー**：複数の指標を比較する際に **行最小値** を適用します。 例：**Row Minimum** （*Revenue*, *Orders*, *Visits*）は、各行のこれらの指標の中の最小値を返します。

>[!TIP]
>
>行最大値と組み合わせると、パフォーマンス範囲を計算したり、パフォーマンスの低い指標を並べて比較してハイライト表示したりできます。
>

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

**ユースケース**：複数の指標の値を 1 行にまとめて加算します。例えば、*売上高* と *税金* を合計してトランザクション合計値を計算したり、様々なソースの *訪問回数* を組み合わせたりします。 これにより、関連指標を 1 つの合計に統合できます。

**計算指標ビルダー**:**行合計** を適用して、複数の指標を組み合わせます。 例：**Row Sum** （*Revenue*, *Tax*）は、分類の各行にこれらの 2 つの指標を追加します。

>[!TIP]
>
>結合された合計を作成したり、関連する業績評価指標を 1 つの計算指標にグループ化したりするために使用します。
>

## 平方根 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="平方根"
>abstract="数値の正の平方根を返します。 数値の平方根は、その数値を 1/2 乗した値です。"

<!-- markdownlint-enable MD034 -->


![効果](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE 行]{type="Neutral"} 数値の正の平方根を返します。数値の平方根は、その数値を 1/2 乗した値です。

| 引数 | 説明 |
|---|---|
| 指標 | 平方根を求める指標です。 |

**使用例**：標準偏差の計算時またはデータセットの値の正規化時の平方根の求めなど、数値または指標の平方根を返します。 これは、高度な統計計算やデータ変換計算に役立ちます。

**計算指標ビルダー**：指標または式に **平方根** を適用します。 例：**平方根** （平方偏差（*Revenue*））は、*Revenue* の標準偏差を返します。

>[!TIP]
>
>指標を均等にスケールしたり、ルート値に依存する他の統計関数をサポートしたりする必要がある場合に使用します。
>

## 標準偏差 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="標準偏差"
>abstract="データのサンプル母集団に基づいて標準偏差（平方偏差の平方根）を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} データのサンプル母集団に基づいて標準偏差（平方偏差の平方根）を返します。

| 引数 | 説明 |
|---|---|
| | 標準偏差を求める指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**：毎日の売上高または訪問数が時間の経過と共にどれくらい一貫しているかを評価するなど、平均からどの程度変化した値を測定します。 これは、パフォーマンスのボラティリティ、安定性、異常な変動を特定するのに役立ちます。

**計算指標ビルダー**:**標準偏差** を *売上高* または *訪問回数* などの指標に適用して、選択した分類または日付範囲内の値の広がりを計算します。 例：**Standard Deviation** （*Revenue*）は、毎日の売上高が平均からどの程度逸脱しているかを示します。

>[!TIP]
>
>*平均* と組み合わせて使用すると、異常値を検出したり、キャンペーン、製品またはセグメント全体でパフォーマンスの一貫性を比較したりできます。
>

## 平方偏差 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="平方偏差"
>abstract="データのサンプル母集団に基づいて平方偏差を返します。"

<!-- markdownlint-enable MD034 -->

![効果](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE テーブル]{type="Neutral"} データのサンプル母集団に基づいて平方偏差を返します。

| 引数 | 説明 |
|---|---|
| 指標 | 平方偏差を計算する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

**ユースケース**：日別売上高やセッション期間が時間の経過と共にどのくらい変化しているかを分析するなど、データセットの値が平均からどのくらい広がっているかを測定します。 これは、パフォーマンスの一貫性や変動の度合いを定量化するのに役立ちます。

**計算指標ビルダー**: **売上高** または *1 訪問あたりの滞在時間* などの指標に *差異* を適用して、平均からの平均自乗偏差を計算します。 例：**Variance** （*Revenue*）は、選択した範囲の平均と異なる売上高の値を示します。

>[!TIP]
>
>**標準偏差** と組み合わせて使用すると、データの変動をより深く理解し、予測できないパフォーマンスの領域を特定できます。
>

VARIANCE の式は次のようになります。

![](assets/variance_eq.png){width="100"}

ここで、*x* はサンプルの平均値 [MEAN(*metric*)](#mean) であり、*n* はサンプルサイズです。


平方偏差を計算するには、数字の列全体を見ます。まず、すべての数字の平均を求めます。平均を求めたら、各数字に対して次の計算を行います。

1. 数字から平均を減算します。

1. 結果を 2 乗します。

1. その結果を合計に加算します。

この計算をすべての列に対して実行したら、1 つの合計を求めます。次に、その合計を列内の項目の数で割ります。 この数値が列の差異になります。 これは単一の数値です。 ただし、数値の列として表示されます。

次の 3 項目列の例では、

| 列 |
|:---:|
| 1 |
| 2 |
| 3 |

この列の平均は 2 です。 この列の平方偏差は、((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3 です。

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

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers-that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

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