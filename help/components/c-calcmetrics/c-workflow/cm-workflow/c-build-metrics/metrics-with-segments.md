---
description: 個々の指標でセグメント化を行うと、1 つのレポート内の指標を比較できます。
title: セグメント化指標
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 31da453887027f5c3a625d014411cf45353e62bf
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 4%

---

# セグメント化指標

[ 計算指標ビルダー ](cm-build-metrics.md#definition-builder) では、指標の定義内にセグメントを適用できます。 セグメントの適用は、分析で指標をデータのサブセットに使用する場合に役立ちます。

>[!NOTE]
>
>セグメント定義は、[ セグメントビルダー ](/help/components/segmentation/segmentation-workflow/seg-build.md) を使用して更新されます。 セグメントに変更を加えると、セグメントが計算指標定義の一部であるかどうかを含め、セグメントが使用されているすべての場所でセグメントが自動的に更新されます。
>

ブランドとやり取りするドイツ人の指標とドイツ国外のユーザーの指標を比較します。 次のような質問に答えることができます。

1. 最も人気のある [ 人気の高いページ ](#popular-pages) を訪問しているドイツ人と外国人の数。
1. 今月、ブランドとオンラインでやり取りしたドイツ人と外国人の数 [ 合計 ](#totals)。
1. 人気のあるページを訪問したドイツ人や国際的な人々の [ 割合 ](#percentages) は何ですか？

以下の節を参照して、セグメント化指標がこれらの質問に答える際にどのように役立つかをご確認ください。 該当する場合は、より詳細なドキュメントへの参照が行われます。

## 人気のあるページ

1. Workspace プロジェクトから [ 計算指標を作成 ](../cm-workflow.md) し、`Germany` という名前を付けます。
1. [ 計算指標ビルダー ](cm-build-metrics.md) 内から、`Germany` というタイトルの [ セグメントを作成 ](/help/components/segmentation/segmentation-workflow/seg-build.md) します。これは「国」フィールドを使用しています。

   >[!TIP]
   >
   >計算指標ビルダーでは、コンポーネント パネルを使用して直接セグメントを作成できます。
   >   

   セグメントは次のようになります。

   ![ セグメント ドイツ ](assets/segment-germany.png)

1. 計算指標ビルダーに戻り、セグメントを使用して計算指標を更新します。

   ![ 計算指標ドイツ ](assets/germany-visits.png)

計算指標の国際バージョンに対して、上記の手順を繰り返します。

1. Workspace プロジェクトから `Non Germany visits` というタイトルの計算指標を作成します。
1. 計算指標ビルダー内から、`Not Germany` というタイトルのセグメントを作成します。このセグメントは、CRM データの CRM 国フィールドを使用して、ユーザーが来ている場所を判断します。

   セグメントは次のようになります。

   ![ セグメント ドイツ ](assets/segment-not-germany.png)

1. 計算指標ビルダーに戻り、セグメントを使用して計算指標を更新します。

   ![ 計算指標ドイツ ](assets/non-germany-visits.png)


1. Analysis Workspaceでプロジェクトを作成します。このプロジェクトでは、ドイツ人およびドイツ人以外の訪問者が訪問したページを確認できます。

   ![ ドイツ人と海外のユーザーを表示するWorkspaceのフリーフォームテーブルビジュアライゼーション ](assets/workspace-german-vs-international.png)


## 合計

1. 総計に基づいて 2 つの新しい計算指標を作成します。 前に作成した各セグメントを開き、セグメントの名前を変更し、**[!UICONTROL 人物]** の **[!UICONTROL 指標タイプ]** を **[!UICONTROL 総計]** に設定して、**[!UICONTROL 名前を付けて保存]** を使用してセグメントを新しい名前で保存します。 例：

   ![ ドイツの合計指標 ](assets/calculated-metric-germany-total.png)

1. 新しいフリーフォームテーブルビジュアライゼーションをWorkspace プロジェクトに追加し、今年のページ総数を表示します。

   ![ ドイツ語と国際の合計人数を示すWorkspaceのフリーフォームテーブルビジュアライゼーション ](assets/workspace-german-vs-international-totals.png)


## 割合

1. 前に作成した計算指標からパーセンテージを計算する 2 つの新しい計算指標を作成します。

   ![ ドイツ人と国際の合計人数の割合を示すWorkspaceのフリーフォームテーブルビジュアライゼーション ](assets/calculated-metric-germany-total-percentage.png)


1. Workspace プロジェクトを更新します。

   ![ ドイツ語と国際の合計人数を示すWorkspaceのフリーフォームテーブルビジュアライゼーション ](assets/workspace-german-vs-international-totals-percentage.png)

