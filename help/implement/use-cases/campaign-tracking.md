---
title: キャンペーントラッキングワークフロー
description: Adobe Analytics を使用して、マーケティング活動を追跡します。
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: ht
source-wordcount: '576'
ht-degree: 100%

---

# キャンペーントラッキングワークフロー

組織がマーケティング活動のパフォーマンスとクリックスルー率を追跡する場合は、次のプロセスを使用できます。次の各手順には、以下の専用の節があり、詳細が記載されています。

1. [トラッキングコード生成プロセスを確立](#establish-a-tracking-code-generation-process)
1. [目的のトラッキングコードをメールに追加](#add-the-desired-tracking-code-to-the-email)
1. [Adobe Analytics 実装を設定または調整し、トラッキングコードデータを含める](#include-campaign-variables-in-your-implementation)
1. [Analysis Workspace でレポートを表示](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/jp/products/campaign/adobe-campaign.html) は、これらの各手順を簡素化し、マーケティング活動から最大限の価値を引き出すのに役立ちます。詳しくは、アドビ担当営業または販売店にお問い合わせください。

## トラッキングコード生成プロセスを確立

組織ごとに、トラッキングコードに対するニーズは異なります。組織によっては、ニーズが最小限のため、手動で作成したトラッキングコードで十分な場合もあります。一方で他の組織では、トラッキングをより詳細に制御したいと考えて、目的のトラッキングコードを作成するために複数のシステムを導入しているところもあります。組織が Adobe Analytics 以外に Google Analytics を使用している場合は、既に `utm` トラッキングコードモデルが確立されている可能性があります。

トラッキングコードの作成方法や生成方法に関わらず、一貫したシステムを導入すると、レポート用にトラッキングコードをグループ化する際に、組織が非常に簡単に対応できます。一貫して構造化されたトラッキングコードを使用して[分類ルール](/help/components/classifications/crb/classification-rule-builder.md)を作成し、カテゴリ別のパフォーマンスに関するインサイトを得ることができます。

## 目的のトラッキングコードを URL に追加

目的のトラッキングコード値を取得したら、広告、ソーシャルメディア、メールなど、オンラインで投稿するリンクにその値を追加できます。これらのトラッキングコードの追加は通常、リンクのクエリ文字列で行います。使用するクエリ文字列パラメーターは、組織のトラッキング要件に応じて異なります。一般的なクエリ文字列パラメーターは、`cid`（キャンペーン ID の略）です。Google Analytics も使用している一部の組織では、`utm_source`、`utm_medium` などの複数のキャンペーンクエリ文字列パラメーターを既に使用している場合があります。

メール内のリンクにクエリ文字列を追加すると、次のようになります。

```text
https://example.com?cid=EM989027
```

## 実装にキャンペーン変数を含める

Adobe Analytics には、組織全体の様々なマーケティング活動を測定するために使用できる専用の[トラッキングコード](/help/components/dimensions/tracking-code.md)ディメンションがあります。ただし、組織が異なれば、トラッキング要件も異なる場合があります。組織の[ソリューションデザインドキュメント](../prepare/solution-design.md)を参照して、適切な変数の適切な値を一貫して追跡することが重要です。

組織がまだキャンペーントラッキングを設定していない場合は、実装を調整して [`campaign`](/help/implement/vars/page-vars/campaign.md) 変数を設定できます。 組織の実装に固有のクエリ文字列パラメーター値を収集する方法については、[`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) メソッドを参照してください。

組織が `utm` クエリ文字列を収集している場合は、次のいずれかを選択できます。

* すべての `utm` クエリ文字列を連結値としてトラッキングコードディメンションに送信します。その後、[分類ルール](/help/components/classifications/crb/classification-rule-builder.md)を使用して、各 `utm` パラメーターに焦点を当てた追加のディメンションを作成できます。このメソッドの学習曲線はより複雑ですが、追加の eVar は使用されません。
* 各 `utm` クエリ文字列を個別の [eVar](/help/components/dimensions/evar.md) に送信します。このメソッドは全体的に実装がより簡単ですが、追加の eVar の使用が必要です。

## Analysis Workspace でレポートを表示

トラッキングコードデータを収集するよう実装を適切に設定したら、Analysis Workspace でレポートを表示できます。

1. [Adobe Experience Cloud](https://experience.adobe.com) にログインし、[!UICONTROL Adobe Analytics] を選択します。
1. [ワークスペースプロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)を作成します。
1. 左側のコンポーネントのリストで、[トラッキングコード](/help/components/dimensions/tracking-code.md)ディメンションをワークスペースキャンバスにドラッグします。
1. [訪問回数](/help/components/metrics/visits.md)や[注文件数](/help/components/metrics/orders.md)などの目的の指標をワークスペースキャンバスの右側にドラッグします。

![キャンペーンのトラッキングレポート](../assets/campaign-tracking-report.png)
