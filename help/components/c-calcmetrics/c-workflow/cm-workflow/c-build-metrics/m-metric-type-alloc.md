---
description: 詳細
title: 指標タイプとアトリビューション
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 21c4d1b591daf7229bd36845e42e2dec473e792f
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 98%

---

# 指標タイプとアトリビューション {#metric-type-attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="モデル"
>abstract="指標のアトリビューションモデルを選択します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="ラストタッチ"
>abstract="訪問者が閲覧した最後のディメンション値に、クレジットの 100％を割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="ファーストタッチ"
>abstract="訪問者が閲覧した最初のディメンション値に、クレジットの 100％を割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="線形"
>abstract="クレジットはすべてのディメンション値に均等に配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="パーティシペーション"
>abstract="訪問者が閲覧したすべてのディメンション値に 100%クレジットされます。<br/>列の合計は誇張されています。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同じタッチ"
>abstract="コンバージョンと同じイベントで発生するディメンション値にのみ、クレジットを割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="同じタッチ"
>abstract="コンバージョンと同じイベントで発生するディメンション値にのみ、クレジットを割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 字型"
>abstract="最初のディメンション値に 40%、最後のディメンション値に 40%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J カーブ"
>abstract="最後のディメンション値に 60%、最初のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J カーブ"
>abstract="最後のディメンション値に 60%、最初のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="逆 J 形"
>abstract="最初のディメンション値に 60%、最後のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="逆 J 形"
>abstract="最初のディメンション値に 60%、最後のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="タイムディケイ"
>abstract="コンバージョンに最も近いディメンション値に、最も多くのクレジットを付与します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="カスタム"
>abstract="独自の位置ベースのアトリビューションの重み付けを定義します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="カスタム"
>abstract="独自の位置ベースのアトリビューションの重み付けを定義します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="アルゴリズム"
>abstract="クレジットは、統計的アルゴリズムに基づいて動的に決定されます。"


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="コンテナ"
>abstract="コンテナを選択して、アトリビューションに必要な範囲を設定します。"


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="ルックバックウィンドウ"
>abstract="この設定により、各コンバージョンに適用されるデータアトリビューションの期間が決まります。"

[計算指標を作成](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)する際に、指標タイプとアトリビューションモデルを指定できます。

## 指標タイプ

計算指標を作成する際に、指標タイプを指定するには：

1. 選択するタイプの指標の横にある歯車アイコンを選択します。

   ![](assets/cm_type_alloc.png)

1. 次のオプションから選択します。

   | 指標タイプ | 定義 |
   |---|---|
   | 標準 | これらの指標は、標準の [!DNL Analytics] レポートで使用される指標と同じです。1 つの標準指標で構成される数式は、その標準指標に対応する計算指標以外の指標と同じデータを表示します。標準指標は、個々の行項目に固有の計算指標を作成する場合に役立ちます。例えば、[購入回数]／[訪問回数]の場合、特定の行項目の購入回数を特定の行項目の訪問回数で割ります。 |
   | 総計 | 各行項目のレポート期間の総計を使用します。1 つの総計指標で構成される数式は、各行項目で同じ合計数を表示します。総計指標は、サイト合計データと比較する計算指標を作成する場合に役立ちます。例えば、[購入回数]／[合計訪問回数]は、特定の行項目への訪問回数だけでなく、サイトへのすべての訪問回数に対する購入回数の割合を示します。 |

## 線形配分の仕組み

[アトリビューション](/help/analyze/analysis-workspace/attribution/overview.md)は、計算指標における配分モデルを評価する方法です。

デフォルト以外のアトリビューションモデルとサポートされるルックバックウィンドウの完全なリストについて詳しくは、[アトリビューションモデルとルックバックウィンドウ](/help/analyze/analysis-workspace/attribution/models.md)を参照してください。

次の例では、レポートで機能する線形配分を使用した計算指標を示します。

| | ヒット 1 | ヒット 2 | ヒット 3 | ヒット 4 | ヒット 5 | ヒット 6 | ヒット 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| 送信データ | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $10 |
| ラストタッチ eVar | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | $10 |
| ファーストタッチ eVar | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | $10 |
| prop 例 | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $10 |

この例では、ヒット 7 で $10 の購入が行われる前に、値 A、B、C がヒット 1、3、4、6 の変数に送信されました。2 番目の行では、ラストタッチでの訪問がベースとなり、ヒット全体に値が持続されています。3 番目の行では、ファーストタッチでの訪問が持続されていることがわかります。最後の行には、持続性のない prop に記録されるデータの内容が示されています。

