---
description: 内部URL フィルターは、サイトの内部で検討するリファラーを識別します。 トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。
title: 内部 URL フィルター
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
TQID: https://experienceleague.adobe.com/J78ImTXRPFm6aMHqrxJXZOUVyG-ETnutipYYo2wrofc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 82%

---

# 内部 URL フィルター

内部 URL フィルターを使用すると、サイト内部と見なすリファラーを特定できます。 トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** > **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL 内部 URL フィルター]**

リファラー（参照ページ）とは、通常、訪問者がサイトにアクセスしたページのことです。 データの歪みを避けるために、内部リファラーを除外することができます。 内部 URL フィルターに依存するディメンションには、以下が含まれます。[リファラー](/help/components/dimensions/referrer.md), [参照ドメイン](/help/components/dimensions/referring-domain.md), [マーケティングチャネル](/help/components/dimensions/marketing-channel.md)、およびその他のトラフィックソースディメンション

[マーケティングチャネルの処理ルール](../marketing-channels/mc-proc-rules.md)では、可能なルール条件として「[!UICONTROL 内部 URL フィルターに一致]」が用意されています。

>[!IMPORTANT]
>
>一部のレポートスイートには、ピリオド (`.`) がデフォルトで設定されています。 このフィルターが存在する場合、すべてのトラフィックは内部トラフィックとして分類されます。 リファラーレポートは、このフィルターが削除され、1 つ以上の目的の内部ドメインに置き換えられるまで機能しません。

* 「**[!UICONTROL 現在のフィルター]**」セクションで既存のフィルターをすべて表示します。
* フィルターを追加するには、「**[!UICONTROL フィルターの追加]**」セクションのテキストボックスを使用して「**[!UICONTROL 追加]**」をクリックします。

フィルターは、完全な URL に対して **次を含む** ロジックを使用して動作します。 Adobeでは、別のサブドメインからのトラフィックが外部トラフィックとして必要な場合を除き、フィルターを作成する際にプロトコル (`https://`)  およびサブドメインを省略することを推奨します。
