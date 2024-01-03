---
description: 内部 URL フィルターは、サイト内部のリファラーを識別します。トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。
title: 内部 URL フィルター
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 31%

---


# 内部 URL フィルター

内部 URL フィルターを使用すると、サイト内部と見なすリファラーを特定できます。 トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** > **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL 内部 URL フィルター]**

リファラー（参照元ページ）は、通常訪問者がサイトを訪問する前に表示したページです。データの歪曲を避けるために、自社の内部リファラーをフィルターして除外できます。内部 URL フィルターに依存するDimensionには、以下が含まれます [リファラー](/help/components/dimensions/referrer.md), [参照ドメイン](/help/components/dimensions/referring-domain.md), [マーケティングチャネル](/help/components/dimensions/marketing-channel.md)、およびその他のトラフィックソースディメンション。

[マーケティングチャネルの処理ルール](../marketing-channels/c-rules.md) &quot;[!UICONTROL 内部 URL フィルターに一致]」を設定します。

>[!IMPORTANT]
>
>一部のレポートスイートには、期間 (`.`) がデフォルトで設定されています。 このフィルターが存在する場合、すべてのトラフィックは内部トラフィックとして分類されます。 リファラーレポートは、このフィルターが削除され、1 つ以上の目的の内部ドメインに置き換えられるまで機能しません。

* 以下の既存のフィルターをすべて表示 **[!UICONTROL 現在のフィルター]** 」セクションに入力します。
* フィルターを追加するには、 **[!UICONTROL フィルターを追加]** 「 」セクションで、「 **[!UICONTROL 追加]**.

フィルターは次を使用して動作します **次を含む** 論理を完全な URL に対して使用します。 Adobeでは、プロトコル (`https://`) およびサブドメイン（別のサブドメインからのトラフィックが外部トラフィックとして必要でない場合）にのみ使用できます。
