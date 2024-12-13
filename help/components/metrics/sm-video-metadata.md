---
title: ストリーミングメディアビデオのメタデータ指標
description: レポートスイートの [!UICONTROL  ビデオメタデータ ] を有効にするときに使用できる指標です。
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 5%

---

# ストリーミングメディアビデオのメタデータ指標

*このページでは、レポートスイートの [!UICONTROL  ビデオメタデータ ] を有効にした場合に使用可能な指標について説明します。 使用可能な寸法については、[ ストリーミングメディアビデオのメタデータの寸法 ](../dimensions/sm-video-metadata.md) を参照してください。*

ストリーミングメディアビデオのメタデータ指標は、ストリーミングメディアコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobeのストリーミングメディアコレクション]** が必要です。 詳しくは、Adobeアカウントチームにお問い合わせください。

[ メディアレポート ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) の **[!UICONTROL ビデオメタデータ]** を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| 認証済み | Adobe認証によってユーザーが許可された場合にトリガーとなるブール値。 | メディア開始、メディア終了 | `a.media.pass.auth` |

{style="table-layout:auto"}
