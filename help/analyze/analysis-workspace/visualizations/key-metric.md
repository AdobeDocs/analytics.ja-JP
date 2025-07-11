---
description: 主要指標の概要ビジュアライゼーションを使用すると、2 つのタイムラインにわたる指標のパフォーマンスを比較できます。
title: 主要指標の概要
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 96%

---

# 主要指標の概要 {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="主要指標の概要"
>abstract="折れ線グラフ、変更概要グラフおよび数値の概要グラフを組み合わせたビジュアライゼーションを作成します。このビジュアライゼーションを使用すると、2 つの期間での重要な指標のトレンドを比較できます。"


>[!BEGINSHADEBOX]

_この記事では、_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** の主要指標の概要ビジュアライゼーションについて説明します。_<br/>_この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** バージョンについて詳しくは、[主要指標の概要](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/visualizations/key-metric)を参照してください。_

>[!ENDSHADEBOX]


![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 主要指標の概要]**&#x200B;ビジュアライゼーションを使用すると、1 つの期間内で重要な指標のトレンドを確認できます。また、2 つの期間にわたる指標のパフォーマンスを比較することもできます。次のような複数のビジュアライゼーションが 1 つのビジュアライゼーションに統合されるメリットがあります。

* プライマリ日付範囲と比較日付範囲での指標のトレンドを表示する&#x200B;**[!UICONTROL 折れ線グラフ]**&#x200B;ビジュアライゼーション

* プライマリ日付範囲と比較日付範囲の間の指標の増減を示す&#x200B;**[!UICONTROL 変化率の概要]**

* 指標の現在の合計値（[!UICONTROL **数値概要**]）

## ユースケース

このビジュアライゼーションは、次のような様々な一般的なユースケースに対応しています。

* アナリストは前年の同じ期間と比較して今月の機会創出の様相を把握しようとしています。

* マーケターは特定のリードタイプのリードジェネレーションが今月から先月にかけてどのように変化したかを調べています。

* エグゼクティブは新規予約が今四半期から前四半期にどのように変化したかを理解したいと考えています。

## 使用

1. ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 主要指標の概要]**&#x200B;ビジュアライゼーションを追加します。 [パネルへのビジュアライゼーションの追加](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。

1. **[!UICONTROL 指標]**、**[!UICONTROL プライマリ日付範囲]**、**[!UICONTROL 比較日付範囲]**（オプション）および&#x200B;**[!UICONTROL フィルター]**（オプション）を選択して、ビジュアライゼーションを設定します。

   ![指標、プライマリ日付範囲、比較日付範囲およびセグメントのオプションを表示する主要指標の設定。](assets/key-metrics-config.png)

   | オプション | 説明 |
   | --- | --- |
   | **[!UICONTROL 指標]** | 調査の対象となる指標を選択します。すべての指標がサポートされています。 |
   | **[!UICONTROL プライマリ日付範囲]** | フリーフォームテーブルの現在の日付範囲。<p>データビューで使用可能な日付範囲から選択します。</p> <p>ビジュアライゼーションがあるパネルで使用されているのと同じ日付範囲を使用する場合は、「[!UICONTROL **パネルの日付範囲**]」を選択します。</p> |
   | **[!UICONTROL 比較日付範囲]** | プライマリ日付範囲の比較対象となる日付範囲。 |
   | **[!UICONTROL セグメント (オプション)]** | この概要で関心のあるセグメント。 |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >「[!UICONTROL **プライマリ日付範囲**]」フィールドが&#x200B;[!UICONTROL **パネル日付範囲**]&#x200B;に設定されている場合、選択した&#x200B;**[!UICONTROL 比較日付範囲]**&#x200B;オプションがプライマリ日付範囲に対して相対的であるか固定であるかに応じて、**[!UICONTROL 比較日付範囲]**&#x200B;が自動的に更新されます。
   >
   >* **相対的**：「**[!UICONTROL 比較日付範囲]**」フィールドがプライマリ日付範囲に相対的なオプション（[!UICONTROL **前日**]、[!UICONTROL **先週の同じ日**]、[!UICONTROL **4 週間前の同じ日**]&#x200B;など）に設定されている場合、「[!UICONTROL **プライマリ日付範囲**]」フィールドを更新すると、**[!UICONTROL 比較日付範囲]**&#x200B;はパネル日付範囲の直後の期間に自動的に更新されます。
   >* **固定：**「[!UICONTROL **比較日付範囲**]」フィールドが固定日付範囲（**2023年2月3日（PT）**&#x200B;など）に設定されている場合、「[!UICONTROL **プライマリ日付範囲**]」フィールドまたはパネル日付範囲に行われた変更は&#x200B;[!UICONTROL **比較日付範囲**]&#x200B;に影響しません。ただし、パネル日付範囲を更新すると、[!UICONTROL **プライマリ日付範囲**]&#x200B;が自動的に更新されます。

1. 「**[!UICONTROL 作成]**」を選択します。

主要指標の概要の出力は次のようになります。

![指標、変更の概要、数値の概要、折れ線グラフを表示する主要指標の出力。](assets/key-metrics.png)

出力を表示する際は、次の点を考慮してください。

* **[!UICONTROL 前の期間]**&#x200B;の折れ線グラフ（常にグレーで表示）は、設定手順の&#x200B;**[!UICONTROL 比較日付範囲]**&#x200B;に対応しています。

* 比較日付範囲が設定時に指定されていない場合やビジュアライゼーション設定で非表示になっている場合は、プライマリ日付範囲の折れ線グラフのみが表示されます。 変更の概要は非表示になります。

* ここから、折れ線グラフの上にマウスポインターを置くと、個々の日の統計情報を表示できます。


## 設定

ビジュアライゼーションを作成した後、元の設定を編集できます。

1. ビジュアライゼーションの上部にある ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL ビジュアライゼーションを設定]**&#x200B;を選択します。

   元の設定ダイアログに戻ります。

1. 必要に応じて設定を変更します。現在の設定をリセットするには、「**[!UICONTROL リセット]**」を選択します。「**[!UICONTROL 作成]**」を選択して、ビジュアライゼーションを再作成します。

## 設定

ビジュアライゼーション設定の一部として、特定の主要指標の概要設定を使用できます。

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 変化率を強調]** | ビジュアライゼーションの中央に目立つ太字で変更概要を表示します |
| **[!UICONTROL 数値を強調]** | ビジュアライゼーションの中央に目立つ太字で数値概要を表示します |
| **[!UICONTROL 凡例を表示]** | ビジュアライゼーションの下部に凡例を表示または非表示にします |
| **[!UICONTROL 注釈を表示]** | 管理者に追加された注釈を表示または非表示にします |
| **[!UICONTROL タイトルを非表示]** | ビジュアライゼーションのタイトルを非表示にします。 |
| **[!UICONTROL 割合 (％)]** | ビジュアライゼーションを数値ではなく割合で表示します。 |
| **[!UICONTROL トレンドラインを表示]** | ビジュアライゼーションにトレンドラインを表示します。 |
| **[!UICONTROL トレンドラインに最大値と最小値を表示]** | プライマリ折れ線グラフと比較折れ線グラフの最小値と最大値を表示または非表示 |
| **[!UICONTROL 比較率とトレンドラインを表示]** | 比較データを表示または非表示にします。 非表示の場合、比較折れ線グラフと変更概要オブジェクトの両方が非表示になります。 |
| **[!UICONTROL 合計数を表示]** | 数値概要を表示または非表示 |
| **[!UICONTROL 生の差異を表示]** | プライマリ日付範囲とセカンダリ日付範囲の指標の合計値の生の差異を表示または非表示 |
| **[!UICONTROL 値を短縮]** | 数値をインテリジェントに短縮するには、「**[!UICONTROL 値を短縮]**」を選択します。選択した場合、短縮の量を定義する数値を入力します。次に例を示します。<br/><table><tr><td>**元の値**</td><td>**短縮**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選択</td><td align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>選択済み、1 に設定</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、2 に設定</td><td align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、2 に設定</td><td align="right">$12.011M</td></tr><tr><td>$12,011,141.25</td><td>選択、3 に設定</td><td align="right">$12.011M</td></tr></table> |

## ビジュアライゼーションの編集

ビジュアライゼーションを作成したら、元の設定を編集できます。

1. ビジュアライゼーションの右上隅にある「![ 編集 ](/help/assets/icons/Edit.svg)」を選択します。


   元の [ 設定ビュー ](#configure) に戻ります。

1. 必要に応じて、指標、プライマリ日付範囲、比較日付範囲またはセグメントを変更します。

>[!MORELIKETHIS]
>
>[パネルへのビジュアライゼーションの追加](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[ビジュアライゼーション設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[ビジュアライゼーションコンテキストメニュー](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)

