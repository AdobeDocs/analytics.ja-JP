---
title: ストリーミングメディア広告指標
description: レポートスイートの [!UICONTROL &#x200B; メディア広告 &#x200B;] を有効にした場合に使用できる指標です。
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%

---

# ストリーミングメディア広告指標

*このページでは、レポートスイートに対して [!UICONTROL &#x200B; メディア広告 &#x200B;] を有効にした場合に使用可能な指標について説明します。 使用可能なディメンションについては、[ ストリーミングメディア広告ディメンション ](../dimensions/sm-ads.md) を参照してください。*

ストリーミングメディア広告指標は、ストリーミングメディアコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobeのストリーミングメディアコレクション]** が必要です。 詳しくは、Adobeアカウントチームにお問い合わせください。

[ メディアレポート ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) の **[!UICONTROL メディア広告]** を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| 広告完了 | ビデオ広告が完了したときにトリガーされます。 | 広告終了 | `a.media.ad.complete` |
| 広告開始 | ビデオ広告の開始時にトリガーされます。 | 広告開始 | `a.media.ad.view` |
| 広告に費やした時間 | 広告の視聴に費やした合計時間（秒）。 | 広告終了 | `a.media.ad.timePlayed` |
| メディアに費やした時間 | すべての再生イベント（メインコンテンツと広告コンテンツの両方）のイベント時間を秒単位で合計します。 | メディアのクローズ | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
