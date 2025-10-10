---
title: ストリーミングメディアサービスと指標
description: レポートスイートの [!UICONTROL  メディア広告 ] を有効にした場合に使用できる指標です。
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 5%

---

# ストリーミングメディアサービスと指標

*このページでは、レポートスイートに対して [!UICONTROL  メディア広告 ] を有効にした場合に使用可能な指標について説明します。 使用可能なディメンションについては、[ ストリーミングメディアサービス広告ディメンション ](../dimensions/sm-ads.md) を参照してください。*

ストリーミングメディアサービスと指標は、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media Ad-on]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [ メディア広告 ](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| 広告完了 | ビデオ広告が完了したときにトリガーされます。 | 広告終了 | `a.media.ad.complete` |
| 広告開始 | ビデオ広告の開始時にトリガーされます。 | 広告開始 | `a.media.ad.view` |
| 広告に費やした時間 | 広告の視聴に費やした合計時間（秒）。 | 広告終了 | `a.media.ad.timePlayed` |
| メディアに費やした時間 | すべての再生イベント（メインコンテンツと広告コンテンツの両方）のイベント時間を秒単位で合計します。 | メディアのクローズ | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
