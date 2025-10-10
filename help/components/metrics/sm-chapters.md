---
title: ストリーミングメディアサービスのチャプター指標
description: レポートスイートの [!UICONTROL &#x200B; メディアチャプター &#x200B;] を有効にした場合に使用可能な指標です。
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 5%

---

# ストリーミングメディアサービスのチャプター指標

*このページでは、レポートスイートに対して [!UICONTROL &#x200B; メディアチャプター &#x200B;] を有効にした場合に使用可能な指標について説明します。 使用可能なディメンションについては、[&#x200B; ストリーミングメディアサービスのチャプターディメンション &#x200B;](../dimensions/sm-chapters.md) を参照してください。*

ストリーミングメディアサービスのチャプター指標は、ストリーミングメディアサービスコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media Ad-on]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の下の [&#x200B; メディアチャプター &#x200B;](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| チャプター完了 | チャプターが完了したときにトリガーを立てるブール値。 | チャプタークローズ | `a.media.chapter.complete` |
| チャプター開始 | チャプター開始時をトリガーにするブール値。 | チャプター開始 | `a.media.chapter.view` |
| チャプターに費やした時間 | チャプターに費やした時間（秒）。 | チャプタークローズ | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
