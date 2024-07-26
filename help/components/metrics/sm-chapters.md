---
title: ストリーミングメディアチャプター指標
description: レポートスイートの [!UICONTROL  メディアチャプター ] を有効にした場合に使用可能な指標です。
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%

---

# ストリーミングメディアチャプター指標

*このページでは、レポートスイートに対して [!UICONTROL  メディアチャプター ] を有効にした場合に使用可能な指標について説明します。 使用可能なディメンションについては、[ ストリーミングメディアチャプターディメンション ](../dimensions/sm-chapters.md) を参照してください。*

ストリーミングメディアチャプター指標は、ストリーミングメディアコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobeのストリーミングメディアコレクションアドオン]** が必要です。 詳しくは、Adobeアカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の下の [ メディアチャプター ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| チャプター完了 | チャプターが完了したときにトリガーを立てるブール値。 | チャプタークローズ | `a.media.chapter.complete` |
| チャプター開始 | チャプター開始時をトリガーにするブール値。 | チャプター開始 | `a.media.chapter.view` |
| チャプターに費やした時間 | チャプターに費やした時間（秒）。 | チャプタークローズ | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
