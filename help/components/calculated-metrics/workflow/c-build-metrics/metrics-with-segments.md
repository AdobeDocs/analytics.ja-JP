---
description: 同じビジュアライゼーション内で指標を比較できる個々の指標をセグメント化する方法について説明します。
title: セグメント化指標
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
TQID: https://experienceleague.adobe.com/t1HtjinGP02YSBQk1Z95t6wIQ0OhuFb14GKfpd8Y9Eg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 463
ht-degree: 1%

---

# セグメント化指標

[計算指標ビルダー](cm-build-metrics.md#definition-builder)では、指標の定義内にセグメントを適用できます。 セグメントの適用は、分析でデータのサブセットに指標を使用する場合に役立ちます。

>[!NOTE]
>
>セグメント定義は、[ セグメントビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md)を通じて更新されます。 セグメントに変更を加えると、セグメントが計算指標の定義の一部であるかどうかも含め、そのセグメントが使用されるあらゆる場所で自動的に更新されます。
>

自社と接触したドイツ人と、それ以外の国や地域の人との指標を比較します。 例えば、次のような質問に答えることができます。

1. 最も人気のある[ ページを訪問しているドイツ人と外国人の数](#popular-pages)。
1. 今月、オンラインで自社と接触したドイツ人と外国人の数（[合計](#totals)）を比較します。
1. あなたの人気ページにアクセスしたドイツ人と外国人の[ パーセンテージ ](#percentages)は何ですか？

以下のセクションでは、セグメント化された指標がこれらの質問に対する回答にどのように役立つかを示しています。 必要に応じて、より詳細なドキュメントを参照します。

## 人気ページ

1. [Workspace プロジェクトから`Germany`という名前の計算指標](../cm-workflow.md)を作成します。
1. [計算指標ビルダー](cm-build-metrics.md)内から、[国フィールドを使用する`Germany`というタイトルのセグメント ](/help/components/segmentation/segmentation-workflow/seg-build.md)を作成します。

   >[!TIP]
   >
   >計算指標ビルダーでは、コンポーネントパネルを使用して直接セグメントを作成できます。
   >   

   セグメントは次のようになります。

   ![ セグメントドイツ ](assets/segment-germany.png)

1. 計算指標ビルダーに戻り、セグメントを使用して計算指標を更新します。

   ![計算指標ドイツ ](assets/germany-visits.png)

計算指標の国際バージョンについて、上記の手順を繰り返します。

1. Workspace プロジェクトから、`Non Germany visits`というタイトルの計算指標を作成します。
1. 計算指標ビルダー内から、`Not Germany`というタイトルのセグメントを作成します。このセグメントは、CRM データからCRMの国フィールドを使用して、ユーザーがどこから来たのかを判断します。

   セグメントは次のようになります。

   ![ セグメントドイツ ](assets/segment-not-germany.png)

1. 計算指標ビルダーに戻り、セグメントを使用して計算指標を更新します。

   ![計算指標ドイツ ](assets/non-germany-visits.png)


1. Analysis Workspaceで、ドイツ人とドイツ人以外の訪問者が訪問したページを見るプロジェクトを作成します。

   ![Workspace自由形式テーブルのビジュアライゼーションで、ドイツ人と外国人が表示されている](assets/workspace-german-vs-international.png)


## 合計

1. 総計に基づいて、2つの新しい計算指標を作成します。 以前に作成した各セグメントを開き、セグメント名を変更し、**[!UICONTROL 人物]**&#x200B;の&#x200B;**[!UICONTROL 指標タイプ]**&#x200B;を&#x200B;**[!UICONTROL グランド合計]**&#x200B;に設定し、**[!UICONTROL 別名で保存]**&#x200B;を使用して、新しい名前を使用してセグメントを保存します。 例：

   ![ ドイツの合計指標](assets/calculated-metric-germany-total.png)

1. Workspace プロジェクトに新しいフリーフォームテーブルのビジュアライゼーションを追加し、今年の合計ページを表示します。

   ![Workspace自由形式テーブルのビジュアライゼーションで、ドイツ人対国際総人数を表示](assets/workspace-german-vs-international-totals.png)


## 割合

1. 先ほど作成した計算指標から割合を計算する、2つの新しい計算指標を作成します。

   ![Workspace自由形式テーブルのビジュアライゼーションでドイツ語と国際合計の人数割合を表示](assets/calculated-metric-germany-total-percentage.png)


1. Workspace プロジェクトを更新します。

   ![Workspace自由形式テーブルのビジュアライゼーションで、ドイツ人対国際総人数を表示](assets/workspace-german-vs-international-totals-percentage.png)

