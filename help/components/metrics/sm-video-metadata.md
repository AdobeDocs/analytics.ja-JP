---
title: ストリーミングメディアサービスのビデオメタデータ指標
description: レポートスイートの [!UICONTROL  ビデオメタデータ ] を有効にするときに使用できる指標です。
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 7%

---

# ストリーミングメディアサービスのビデオメタデータ指標

*このページでは、レポートスイートの [!UICONTROL  ビデオメタデータ ] を有効にした場合に使用可能な指標について説明します。 使用可能な寸法については、[ ストリーミングメディアサービスのビデオメタデータの寸法 ](../dimensions/sm-video-metadata.md) を参照してください。*

ストリーミングメディアサービスのビデオメタデータ指標は、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [ ビデオメタデータ ](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 認証済み]** | Adobe認証で許可された場合にトリガーとなるブール値。 | メディア開始、メディア終了 | `a.media.pass.auth` | `xdm.mediaCollection.`<br>`sessionDetails.authorized`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.authorized` |
