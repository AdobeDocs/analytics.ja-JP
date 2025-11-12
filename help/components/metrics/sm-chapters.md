---
title: ストリーミングメディアサービスのチャプター指標
description: レポートスイートの [!UICONTROL  メディアチャプター ] を有効にした場合に使用可能な指標です。
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 6%

---

# ストリーミングメディアサービスのチャプター指標

*このページでは、レポートスイートに対して [!UICONTROL  メディアチャプター ] を有効にした場合に使用可能な指標について説明します。 使用可能なディメンションについては、[ ストリーミングメディアサービスのチャプターディメンション ](../dimensions/sm-chapters.md) を参照してください。*

ストリーミングメディアサービスのチャプター指標は、ストリーミングメディアサービスコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の下の [ メディアチャプター ](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL チャプター完了]** | チャプターが完了したときにトリガーを立てるブール値。 | チャプタークローズ | `a.media.chapter.complete` | `xdm.mediaReporting.`<br>`chapterDetails.isCompleted` |
| **[!UICONTROL チャプター開始]** | チャプター開始時をトリガーにするブール値。 | チャプター開始 | `a.media.chapter.view` | `xdm.mediaReporting.`<br>`chapterDetails.isStarted` |
| **[!UICONTROL チャプターに費やした時間]** | チャプターに費やした時間（秒）。 | チャプタークローズ | `a.media.chapter.timePlayed` | `xdm.mediaReporting.`<br>`chapterDetails.timePlayed` |
