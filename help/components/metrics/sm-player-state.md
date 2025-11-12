---
title: ストリーミングメディアサービスプレーヤーの状態トラッキング指標
description: レポートスイートに対して [!UICONTROL &#x200B; プレーヤーステートトラッキング &#x200B;] を有効にすると使用可能な指標です。
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 2%

---

# ストリーミングメディアサービスプレーヤーの状態トラッキング指標

ストリーミングメディアサービスプレーヤー状態トラッキング指標は、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [&#x200B; プレーヤーの状態のトラッキング &#x200B;](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL クローズドキャプションの影響を受けるストリーム]** | 再生セッション中に 1 つ以上のクローズドキャプション状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL クローズドキャプションのカウント]** | ビデオがクローズドキャプション状態になった回数。 | メディアのクローズ | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL クローズドキャプションの合計期間]** | ビデオがクローズドキャプション状態であった時間（秒）。 | メディアのクローズ | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL フルスクリーンの影響を受けるストリーム]** | 再生セッション中にフルスクリーン状態が少なくとも 1 つ発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 全画面表示カウント]** | ビデオがフルスクリーン状態になった回数。 | メディアのクローズ | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 全画面表示の合計時間]** | ビデオが全画面状態だった時間（秒）。 | メディアのクローズ | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL フォーカス中のの影響を受けるストリーム]** | 再生セッション中に 1 つ以上のフォーカス中状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL インフォーカスのカウント]** | ビデオがフォーカス中状態になった回数。 | メディアのクローズ | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL フォーカス中合計時間]** | ビデオがフォーカス中状態だった時間（秒）。 | メディアのクローズ | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL ミュートの影響を受けるストリーム]** | 再生セッション中に少なくとも 1 つのミュート状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL カウントをミュート]** | ビデオがミュート状態になった回数。 | メディアのクローズ | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 合計時間をミュート]** | ビデオがミュート状態であった時間（秒）。 | メディアのクローズ | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL ピクチャーインピクチャーの影響を受けるストリーム]** | 再生セッション中に 1 つ以上のピクチャーインピクチャー状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL ピクチャーインピクチャーのカウント]** | ビデオがピクチャーインピクチャー状態になった回数。 | メディアのクローズ | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL ピクチャーインピクチャーの合計時間]** | ビデオがピクチャーインピクチャー状態であった時間（秒）。 | メディアのクローズ | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
