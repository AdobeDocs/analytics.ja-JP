---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: Analysis Workspace の指標
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: c1b679dab7b66754ae4b6fd7503243f40d0f2178
workflow-type: ht
source-wordcount: '416'
ht-degree: 100%

---

# 指標

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

## 指標のタイプ

アドビでは、Analysis Workspace で使用するためのいくつかのタイプの指標を提供しています。

* **標準指標**：プロジェクトで使用するほとんどの指標は標準指標です。例には、[ページビュー数](/help/components/metrics/page-views.md)、[収益](/help/components/metrics/revenue.md)または[カスタムイベント](/help/components/metrics/custom-events.md)が含まれます。詳しくは、コンポーネントユーザーガイドの[指標の概要](/help/components/metrics/overview.md)を参照してください。

  ![標準指標](assets/standard-metric.png)

* **計算指標**：標準指標、静的数値、アルゴリズム関数に基づくユーザー定義の指標です。ユーザー定義の計算指標では、使用可能なコンポーネントのリストに電卓アイコンが表示されます。詳しくは、コンポーネントユーザーガイドの[計算指標の概要](/help/components/c-calcmetrics/cm-overview.md)を参照してください。

  ![計算指標](assets/calculated-metric.png)

* **計算指標テンプレート**：計算指標と同様に動作するアドビ定義の指標です。これらを Workspace プロジェクトでそのまま使用することも、コピーを保存してロジックをカスタマイズすることもできます。計算指標テンプレートでは、使用可能なコンポーネントのリストに Adobe アイコンが表示されます。

  ![計算指標テンプレート](assets/calculated-metric-template.png)

## Analysis Workspace での指標の使用

指標は、Analysis Workspace 内で様々な方法で使用できます。 次のことができます。

* 指標を空のフリーフォームテーブルにドラッグすると、プロジェクトの日付期間にわたるその指標のトレンドを確認できます。

* ディメンションが存在する場合に指標をドラッグすると、その指標を各ディメンション項目と比較して確認できます。

* 指標を既存の指標ヘッダーの上にドラッグすると、指標を置き換えることができます。

* 指標をヘッダーの横にドラッグすると、両方の指標を並べて確認できます。

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## 計算指標

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連しているかを簡単に確認できます。計算指標を作成する方法はいくつかあります。

* 左側にあるコンポーネントのリストの下で、指標ヘッダーの横にあるプラスアイコンをクリックします。
* **[!UICONTROL コンポーネント]**／**[!UICONTROL 計算指標]**／**[!UICONTROL 追加]**&#x200B;に移動します。
* 1 つ以上のヘッダー列のセルが選択されている場合は、列見出しを右クリックして、**[!UICONTROL 選択から指標を作成]**&#x200B;に移動します。このオプションでは、計算指標ルールビルダーを使用しなくても、計算指標が自動的に作成されます。

[計算指標： 実装なしの指標](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ja)（3:42）

## 様々なアトリビューションモデルとの指標の比較

アトリビューションモデルを別のアトリビューションモデルと素早く簡単に比較したい場合は、指標を右クリックし、「**[!UICONTROL アトリビューションモデルを比較]**」を選択します。

![アトリビューションの比較](assets/compare-attribution.png)

これにより、指標にドラッグして設定を 2 回おこなわなくても、アトリビューションモデルをすばやく簡単に相互比較できます。

## [!UICONTROL 累積平均] 関数を使用した指標スムージングの適用

以下は、このトピックに関するビデオです。

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)
