---
title: 直帰数（指標）
description: 訪問で、「ページ」ディメンション項目が変更されなかった回数。
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
TQID: https://experienceleague.adobe.com/iDXuwf-Ls1N7VzmtZiMRISLbSEtHOtDTeoddfDEiAwA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 34%

---

# 直帰数

*このヘルプページでは、「直帰数」が指標としてどのように機能するかを説明します。 詳しくは、[直帰数](../dimensions/single-page-visits.md)ディメンションを参照してください。*

**[!UICONTROL 単一ページ訪問回数]** [指標](overview.md)は、[&#x200B; ページ &#x200B;](../dimensions/page.md) ディメンション項目が訪問全体に1つの値のみを含む訪問回数を示します。 この指標は、短い訪問を表示したいが、[[!UICONTROL バウンス]](bounces.md)ほど厳しいルールを持たないディメンションのコンテキストで役立ちます。

## この指標の計算方法

この指標の定義は、[[!UICONTROL 繰り返しインスタンスをカウント &#x200B;]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)するプロジェクト設定によって異なります。

* **[!UICONTROL 繰り返しインスタンスをカウント &#x200B;]有効**: [!UICONTROL &#x200B; ページ &#x200B;] ディメンションに訪問の1つの値が含まれている訪問回数をカウントします。 訪問者がページを再読み込みすると、1回のページ訪問として失格されます。
* **[!UICONTROL 繰り返しインスタンスをカウント &#x200B;]無効**: [!UICONTROL &#x200B; ページ &#x200B;] ディメンションに訪問全体に対して1つの一意の値が含まれている訪問回数をカウントします。

&#39;[!UICONTROL 繰り返しインスタンスの数]&#39; プロジェクト設定に関係なく、この指標は次のルールに従います。

* 訪問者がリンクトラッキング呼び出しを実行した場合、訪問は引き続き単一ページ訪問として認定されます（[!UICONTROL Page] ディメンションはすべてのリンクトラッキング呼び出しから削除されます）。
* [!UICONTROL &#x200B; ページ &#x200B;]のディメンションが2番目の一意の値に変更されると、その訪問は1回のページ訪問として認定されなくなります。

指標の比較については、「[単一アクセス](single-access.md)」を参照してください。
