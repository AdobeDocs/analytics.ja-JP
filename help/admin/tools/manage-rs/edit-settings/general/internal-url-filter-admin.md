---
description: 内部 URL フィルターは、サイト内部と見なされるリファラーを識別します。 トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。
title: 内部 URL フィルター
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 82%

---


# 内部 URL フィルター

内部 URL フィルターを使用すると、サイト内部と見なすリファラーを特定できます。トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** > **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL 内部 URL フィルター]**

リファラー（参照ページ）は、通常、訪問者がサイトにエントリしたページです。 データのゆがみを防ぐには、内部リファラーを除外します。 内部 URL フィルターに依存するディメンションには、以下が含まれます。[リファラー](/help/components/dimensions/referrer.md), [参照ドメイン](/help/components/dimensions/referring-domain.md), [マーケティングチャネル](/help/components/dimensions/marketing-channel.md)、およびその他のトラフィックソースディメンション

[マーケティングチャネルの処理ルール](../marketing-channels/mc-proc-rules.md)では、可能なルール条件として「[!UICONTROL 内部 URL フィルターに一致]」が用意されています。

>[!IMPORTANT]
>
>一部のレポートスイートには、ピリオド (`.`) がデフォルトで設定されています。このフィルターが存在する場合、すべてのトラフィックは内部トラフィックとして分類されます。 リファラーレポートは、このフィルターが削除され、1 つ以上の目的の内部ドメインに置き換えられるまで機能しません。

* 「**[!UICONTROL 現在のフィルター]**」セクションで既存のフィルターをすべて表示します。
* フィルターを追加するには、「**[!UICONTROL フィルターの追加]**」セクションのテキストボックスを使用して「**[!UICONTROL 追加]**」をクリックします。

フィルターは、完全な URL に対して **次を含む** ロジックを使用して動作します。Adobeでは、別のサブドメインからのトラフィックが外部トラフィックとして必要な場合を除き、フィルターを作成する際にプロトコル (`https://`)  およびサブドメインを省略することを推奨します。
