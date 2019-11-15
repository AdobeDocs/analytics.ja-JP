---
description: 'null'
title: セグメント
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# セグメント {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

コンポーネントメニューのセグメントレールには、次のアイコンで示されるようにセグメントとセグメントテンプレートが表示されます。

![](assets/segment_icons.png)

[YouTubeでのAnalysis Workspaceでのセグメントの使用](https://www.youtube.com/watch?v=QlUCdQDnni4)(6:46)

## セグメントの作成 {#section_693CFADA668B4542B982446C2B4CF0F5}

任意の種類のコンポーネント（ディメンション、ディメンション項目、イベント、指標、セグメント、セグメントテンプレート、日付範囲）をパネルの上部にあるセグメントドロップゾーンにドロップすることで、セグメントを即座に作成できます。

コンポーネントの種類はセグメントに自動変換されます。または、「セグメントを追加」ドロップボックスで「+」記号をクリックします。

次の点に注意してください。

* 次の種類のコンポーネントをセグメントゾーンにドロップすることは&#x200B;**できません**：セグメントを作成できない計算指標およびディメンション／指標。
* Analysis Workspace では、すべてのディメンションおよびイベントに対して、「存在する」ヒットセグメントを作成します。例：「eVar1 が存在するヒット」または「event1 が存在するヒット」
* セグメントドロップゾーンで「未指定」または「なし」がドロップされた場合は、セグメント化で正しく処理されるように、自動的に「存在しない」セグメントに変換されます。

![](assets/segment-dropzone.png)

> [!NOTE] この方法で作成されたセグメントは、プロジェクトの内部にあります。

次の手順に従うことで、これらのセグメントを公開（グローバル）できます。

1. ドロップゾーンのセグメントの上にマウスポインターを置いて、「i」アイコンをクリックします。
1. In the information panel that displays, click **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

フリーフォームプロジェクトにセグメントを適用するには、他にもいくつかの方法があります。

| アクション | 説明 |
|--- |--- |
| 選択からセグメントを作成 | インラインセグメントを作成します。行を選択して、選択範囲を右クリックし、インラインセグメントを作成します。このセグメントは、オープンプロジェクトにのみ適用し、Analytics セグメントとして保存されません。1.行を選択します。  2.選択範囲を右クリックします。  3. Click *Create segment from selection*. |
| コンポーネント／新しいセグメント | セグメントビルダーを表示します。See [Segment Builder](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about segmentation. |
| 共有/プロジェクトを共有または共有/プロジェクトデータをキュレーション | In [Curate and Share](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how segments that you apply to the project are available in shared analysis for the recipient. |
| ディメンションとしてセグメントを使用 | ビデオ:[Analysis Workspace でセグメントをディメンションとして使用する](https://www.youtube.com/watch?v=WmSdReKTWto&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=39) |
