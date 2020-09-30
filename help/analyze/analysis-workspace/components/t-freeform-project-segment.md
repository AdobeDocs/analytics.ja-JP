---
description: 'null'
title: セグメント
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 94%

---


# セグメント {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## セグメントパネル {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

コンポーネントメニューのセグメントパネルには、次のアイコンで示されるようにセグメントとセグメントテンプレートが表示されます。

![](assets/segment_icons.png)

[Analysis Workspace でのセグメントの使用](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-in-analysis-workspace.html)（6:46）

## セグメントの作成 {#section_693CFADA668B4542B982446C2B4CF0F5}

任意の種類のコンポーネント（ディメンション、ディメンション項目、イベント、指標、セグメント、セグメントテンプレート、日付範囲）をパネルの上部にあるセグメントドロップゾーンにドロップすることで、セグメントを即座に作成できます。

コンポーネントの種類はセグメントに自動変換されます。また、「セグメントを追加」ドロップダウンの「+」記号をクリックすることもできます。

次の点に注意してください。

* 次の種類のコンポーネントをセグメントゾーンにドロップすることは&#x200B;**できません**：セグメントを作成できない計算指標およびディメンション／指標。
* Analysis Workspace では、すべてのディメンションおよびイベントに対して、「存在する」ヒットセグメントを作成します。例：「eVar1 が存在するヒット」または「event1 が存在するヒット」
* 「未指定」または「なし」がセグメントドロップゾーンにドロップされると、セグメントで正しく扱えるように、自動的に「存在しない」セグメントに変換されます。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>この方法で作成されたセグメントは、プロジェクト内部にあります。

次の手順に従うことで、これらのセグメントを公開（グローバル）できます。

1. ドロップゾーンのセグメントの上にマウスポインターを置いて、「i」アイコンをクリックします。
1. 表示される情報パネルで、「**[!UICONTROL 公開する]**」をクリックします。

   ![](assets/segment-info.png)

## セグメントを適用するその他の方法 {#section_10FF2E309BA84618990EA5B473015894}

フリーフォームプロジェクトにセグメントを適用するには、他にもいくつかの方法があります。

| アクション | 説明 |
|--- |--- |
| 選択からセグメントを作成 | インラインセグメントを作成します。行を選択して、選択範囲を右クリックし、インラインセグメントを作成します。このセグメントは、オープンプロジェクトにのみ適用し、Analytics セグメントとして保存されません。1. 行を選択します。2. 選択範囲を右クリックします。3. 「*選択からセグメントを作成*」をクリックします。 |
| コンポーネント／新しいセグメント | セグメントビルダーを表示します。セグメント化について詳しくは、[セグメントビルダー](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-build.html)を参照してください。 |
| 共有／プロジェクトを共有または共有／プロジェクトデータをキュレート | [キュレーションおよび共有](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6)では、プロジェクトに適用するセグメントを、受信者に共有された分析で使用する方法について学習します。 |
| ディメンションとしてセグメントを使用 | ビデオ：[Analysis Workspace でセグメントをディメンションとして使用する](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/components/segmentation/using-segments-as-dimensions-in-analysis-workspace.html) |
