---
title: ストリーミングメディアサービスと指標
description: レポートスイートの [!UICONTROL &#x200B; メディア広告 &#x200B;] を有効にした場合に使用できる指標です。
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 6%

---

# ストリーミングメディアサービスと指標

*このページでは、レポートスイートに対して [!UICONTROL &#x200B; メディア広告 &#x200B;] を有効にした場合に使用可能な指標について説明します。 使用可能なディメンションについては、[&#x200B; ストリーミングメディアサービス広告ディメンション &#x200B;](../dimensions/sm-ads.md) を参照してください。*

ストリーミングメディアサービスと指標は、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [&#x200B; メディア広告 &#x200B;](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 広告完了]** | ビデオ広告が完了したときにトリガーされます。 | 広告終了 | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL 広告開始]** | ビデオ広告の開始時にトリガーされます。 | 広告開始 | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL 広告視聴時間]** | 広告の視聴に費やした合計時間（秒）。 | 広告終了 | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL メディアに費やした時間]** | すべての「[!UICONTROL &#x200B; 再生 &#x200B;]」イベント（メインコンテンツと広告コンテンツの両方）のイベント時間を秒単位で合計します。 | メディアのクローズ | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
