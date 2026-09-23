---
title: 単一ページ訪問（指標）
description: 訪問で、「ページ」ディメンション項目が変更されなかった回数。
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
TQID: https://experienceleague.adobe.com/iDXuwf-Ls1N7VzmtZiMRISLbSEtHOtDTeoddfDEiAwA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 34%
---
# 直帰数

>[!BEGINSHADEBOX]

*このヘルプページでは、「直帰数」が指標としてどのように機能するかを説明します。 詳しくは、[直帰数](../dimensions/single-page-visits.md)ディメンションを参照してください。*

>[!ENDSHADEBOX]

**[!UICONTROL 単一ページ訪問回数]** [指標](overview.md)は、[ ページ ](../dimensions/page.md) ディメンション項目が訪問全体に1つの値のみを含む訪問回数を示します。 この指標は、短い訪問を表示したいが、[[!UICONTROL バウンス]](bounces.md)ほど厳しいルールを持たないディメンションのコンテキストで役立ちます。

## この指標の計算方法

この指標の定義は、[[!UICONTROL 繰り返しインスタンスをカウント ]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)するプロジェクト設定によって異なります。

* **[!UICONTROL 繰り返しインスタンスをカウント ]有効**: [!UICONTROL  ページ ] ディメンションに訪問の1つの値が含まれている訪問回数をカウントします。 訪問者がページを再読み込みすると、1回のページ訪問として失格されます。
* **[!UICONTROL 繰り返しインスタンスをカウント ]無効**: [!UICONTROL  ページ ] ディメンションに訪問全体に対して1つの一意の値が含まれている訪問回数をカウントします。

&#39;[!UICONTROL 繰り返しインスタンスの数]&#39; プロジェクト設定に関係なく、この指標は次のルールに従います。

* 訪問者がリンクトラッキング呼び出しを実行した場合、訪問は引き続き単一ページ訪問として認定されます（[!UICONTROL Page] ディメンションはすべてのリンクトラッキング呼び出しから削除されます）。
* [!UICONTROL  ページ ]のディメンションが2番目の一意の値に変更されると、その訪問は1回のページ訪問として認定されなくなります。

指標の比較については、「[単一アクセス](single-access.md)」を参照してください。
