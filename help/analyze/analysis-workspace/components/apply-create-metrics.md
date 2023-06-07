---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: Analysis Workspace の指標
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: c1b679dab7b66754ae4b6fd7503243f40d0f2178
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 24%

---

# 指標

指標を使用すると、Analysis Workspaceでデータポイントを定量化できます。 最も一般的に、ビジュアライゼーションの列として使用され、ディメンションに結び付けられます。

## 指標のタイプ

Adobeは、Analysis Workspaceで使用する複数のタイプの指標を提供します。

* **標準指標**:プロジェクトで使用するほとんどの指標は標準指標です。 以下に例を示します。 [ページビュー数](/help/components/metrics/page-views.md), [売上高](/help/components/metrics/revenue.md)または [カスタムイベント](/help/components/metrics/custom-events.md). 詳しくは、 [指標の概要](/help/components/metrics/overview.md) （コンポーネントユーザーガイド）を参照してください。

   ![標準指標](assets/standard-metric.png)

* **計算指標**:標準指標、静的数値、アルゴリズム関数に基づくユーザー定義の指標。 ユーザー定義の計算指標では、使用可能なコンポーネントのリストに計算ツールアイコンが表示されます。 詳しくは、 [計算指標の概要](/help/components/c-calcmetrics/cm-overview.md) （コンポーネントユーザーガイド）を参照してください。

   ![計算指標](assets/calculated-metric.png)

* **計算指標テンプレート**:Adobe定義の指標で、計算指標と同じ動作をします。 これらは、Workspace プロジェクト内でそのまま使用することも、コピーを保存してロジックをカスタマイズすることもできます。 計算指標テンプレートは、使用可能なAdobeのリストに指標アイコンを表示します。

   ![計算指標テンプレート](assets/calculated-metric-template.png)

## Analysis Workspaceでの指標の使用

指標は、Analysis Workspace内の様々な方法で使用できます。 次のことができます。

* 空のフリーフォームテーブルに指標をドラッグして、その指標がプロジェクトの日付期間にトレンド表示されていることを確認します。

* ディメンションが存在する場合に指標をドラッグして、各ディメンション項目と比較した指標を表示します。

* 既存の指標ヘッダーの上に指標をドラッグして置き換えます。

* ヘッダーの横に指標をドラッグして、両方の指標を並べて表示します。

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## 計算指標 

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連しているかを簡単に確認できます。 計算指標を作成する方法はいくつかあります。

* 左側のコンポーネントのリストの下にある「指標」ヘッダーの横にあるプラスアイコンをクリックします。
* に移動します。 **[!UICONTROL コンポーネント]** > **[!UICONTROL 計算指標]** > **[!UICONTROL 追加]**.
* 列見出しを右クリック > **[!UICONTROL 選択から指標を作成]** （1 つ以上のヘッダー列のセルが選択されている場合）。 このオプションを選択すると、計算指標ルールビルダーを使用しなくても、計算指標が自動的に作成されます。

[計算指標： 実装なしの指標](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ja)（3:42）

## 様々なアトリビューションモデルとの指標の比較

アトリビューションモデルを別のアトリビューションモデルと素早く簡単に比較したい場合は、指標を右クリックし、「**[!UICONTROL アトリビューションモデルを比較]**」を選択します。

![アトリビューションの比較](assets/compare-attribution.png)

これにより、指標にドラッグして設定を 2 回おこなわなくても、アトリビューションモデルをすばやく簡単に相互比較できます。

## [!UICONTROL 累積平均] 関数を使用した指標スムージングの適用

以下は、このトピックに関するビデオです。

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)
