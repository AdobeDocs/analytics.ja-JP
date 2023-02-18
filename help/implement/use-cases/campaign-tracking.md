---
title: キャンペーントラッキングワークフロー
description: Adobe Analyticsを使用してマーケティング活動を追跡します。
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: c118d42667c4a1af55929834b87d148a5973bed9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# キャンペーントラッキングワークフロー

組織がマーケティング活動のパフォーマンスとクリックスルー率を追跡する場合は、次のプロセスを使用できます。 これらの各手順には、詳細を説明する専用の節があります。

1. [トラッキングコード生成プロセスの確立](#establish-a-tracking-code-generation-process)
1. [目的のトラッキングコードを E メールに追加します](#add-the-desired-tracking-code-to-the-email)
1. [トラッキングコードデータを含めるようにAdobe Analyticsの実装を設定または調整する](#include-campaign-variables-in-your-implementation)
1. [Analysis Workspaceでレポートを表示](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) では、これらの各手順を簡素化して、マーケティング活動の最大限の価値を引き出すことができます。 詳しくは、Adobeのセールス担当者にお問い合わせください。

## トラッキングコード生成プロセスの確立

トラッキングコードには、組織ごとに異なるニーズがあります。 組織によっては、手動で作成したトラッキングコードで十分な量を超えるニーズが最小限に抑えられている場合があります。 その他の組織では、トラッキングの制御を強化し、必要なトラッキングコードを作成するために複数のシステムを用意しておく必要があります。 組織がAdobe Analytics以外のGoogle Analyticsを使用している場合は、既に `utm` トラッキングコードモデルが確立されました。

トラッキングコードの作成方法や生成方法に関係なく、一貫性のあるシステムを採用することで、レポート用にトラッキングコードをまとめてグループ化する際に、時間をかけやすくすることができます。 一貫した構造を持つトラッキングコードを使用すると、 [分類ルール](/help/components/classifications/crb/classification-rule-builder.md) これにより、カテゴリーパフォーマンスに関するインサイトを得ることができます。

## 目的のトラッキングコードを URL に追加します。

目的のトラッキングコードの値を取得したら、広告、ソーシャルメディア、電子メールなど、オンラインで投稿する任意のリンクに追加できます。 これらのトラッキングコードの追加は、通常、リンクのクエリ文字列でおこなわれます。 使用するクエリー文字列パラメーターは、組織のトラッキング要件に応じて異なります。一般的なクエリー文字列パラメーターは `cid` （キャンペーン ID の略語）。 Google Analyticsも使用する組織には、 `utm_source`, `utm_medium`など。

E メール内のリンクにクエリー文字列を追加すると、次のようになります。

```text
https://example.com?cid=EM989027
```

## 実装にキャンペーン変数を含める

Adobe Analyticsには専用の [トラッキングコード](/help/components/dimensions/tracking-code.md) ディメンションを使用して、組織全体の様々なマーケティング活動を測定できます。 ただし、組織が異なれば、トラッキング要件が異なる場合があります。 組織の [ソリューションデザインドキュメント](../prepare/solution-design.md) を使用して、適切な変数内で適切な値を一貫して追跡する必要があります。

まだキャンペーントラッキングを設定していない場合は、実装を調整して [`campaign`](/help/implement/vars/page-vars/campaign.md) 変数を使用します。 詳しくは、 [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) メソッドを使用して、組織の実装に固有のクエリー文字列パラメーター値を収集する方法を学習します。

組織が `utm` クエリ文字列では、次のいずれかを選択できます。

* すべて送信 `utm` クエリ文字列を連結された値としてトラッキングコードディメンションに取り込みます。 その後、 [分類ルール](/help/components/classifications/crb/classification-rule-builder.md) それぞれに焦点を当てた追加のディメンションを作成するには `utm` パラメーター。 この方法では、より複雑な学習曲線を作成できますが、追加の eVar は使用されません。
* それぞれ送信 `utm` クエリ文字列を別の [eVar](/help/components/dimensions/evar.md). この方法は、全体的に実装するのにより簡単ですが、追加の eVar を使用する必要があります。

## Analysis Workspaceでレポートを表示

トラッキングコードデータを収集するように実装を適切に設定したら、Analysis Workspaceでレポートを表示できます。

1. にログインします。 [Adobe Experience Cloud](https://experience.adobe.com) を選択し、 [!UICONTROL Adobe Analytics].
1. の作成 [Workspace プロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. 左側のコンポーネントのリストで、 [トラッキングコード](/help/components/dimensions/tracking-code.md) ディメンションをワークスペースキャンバスに追加します。
1. 目的の指標（例： ）をドラッグします。 [訪問回数](/help/components/metrics/visits.md) または [注文](/help/components/metrics/orders.md) をワークスペースキャンバスの右側に表示します。

![キャンペーントラッキングレポート](../assets/campaign-tracking-report.png)
