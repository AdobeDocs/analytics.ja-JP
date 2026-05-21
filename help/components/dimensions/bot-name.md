---
title: ボット名
description: Bot ルールに一致するボットの名前。
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 7%

---

# ボット名

「ボット名」 [&#x200B; ディメンション &#x200B;](overview.md)には、[&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)を使用して検出されたボットの名前が表示されます。 これらのルールは、デフォルトのIAB ルールまたは組織が設定するカスタムボットルールにすることができます。 これは、どのボットがサイトにアクセスしているか、どのボットが最も多くのトラフィックを生み出しているかなどについて詳しく知りたい場合に役立ちます。

[!UICONTROL &#x200B; ボットルール &#x200B;]に一致するヒットは、このディメンション、[&#x200B; ボット発生](../metrics/bot-occurrences.md)、[&#x200B; ボットページビュー](../metrics/bot-page-views.md)を除くすべてのAnalytics レポートから自動的にフィルタリングされます。 このディメンションとこれら2つの指標を使用して、どのボットデータがレポートの残りの部分から除外されるかを確認できます。

ボットレポートはレポートスイートデータの残りの部分から分離されているため、このディメンションでは次のディメンションと指標のみがサポートされています。

* [ページ](page.md)
* 時間ベースのディメンション （例：[日](day.md)、[週](week.md)、[月](month.md)）
* [ボットの発生件数](../metrics/bot-occurrences.md)
* [ボットページビュー数](../metrics/bot-page-views.md)

このディメンションで他のディメンションまたは指標を使用しても、データは返されません。

## このディメンションへのデータ入力

[&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)を有効にしている場合、このディメンションは自動的にデータを収集します。 [!UICONTROL &#x200B; ボットルール &#x200B;]をまだ有効にしていない場合、このディメンションはAnalysis Workspaceに表示されません。

## ディメンション項目

各ディメンション項目には、IABまたはカスタムボットルール条件に一致するボットの名前が一覧表示されます。
