---
title: ストリーミングメディアプレーヤーの状態トラッキング指標
description: レポートスイートに対して [!UICONTROL &#x200B; プレーヤーステートトラッキング &#x200B;] を有効にすると使用可能な指標です。
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# ストリーミングメディアプレーヤーの状態トラッキング指標

ストリーミングメディアプレーヤーの状態トラッキング指標は、ストリーミングメディアコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobeのストリーミングメディアコレクション]** が必要です。 詳しくは、Adobeアカウントチームにお問い合わせください。

[ メディアレポート ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) の **[!UICONTROL プレーヤーの状態のトラッキング]** を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| クローズドキャプションの影響を受けたストリーム | 再生セッション中に 1 つ以上のクローズドキャプション状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.closedcaptioning.set` |
| クローズドキャプションのカウント | ビデオがクローズドキャプション状態になった回数。 | メディアのクローズ | `a.media.states.closedcaptioning.count` |
| クローズドキャプションの合計期間 | ビデオがクローズドキャプション状態であった時間（秒）。 | メディアのクローズ | `a.media.states.closedcaptioning.time` |
| フルスクリーンの影響を受けるストリーム | 再生セッション中にフルスクリーン状態が少なくとも 1 つ発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.fullscreen.set` |
| フルスクリーン数 | ビデオがフルスクリーン状態になった回数。 | メディアのクローズ | `a.media.states.fullscreen.count` |
| 全画面表示の合計時間 | ビデオが全画面状態だった時間（秒）。 | メディアのクローズ | `a.media.states.fullscreen.time` |
| がフォーカス中に影響を受けたストリーム | 再生セッション中に 1 つ以上のフォーカス中状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.infocus.set` |
| フォーカス中のカウント | ビデオがフォーカス中状態になった回数。 | メディアのクローズ | `a.media.states.infocus.count` |
| フォーカス中の合計時間 | ビデオがフォーカス中状態だった時間（秒）。 | メディアのクローズ | `a.media.states.infocus.time` |
| ミュートの影響を受けるストリーム | 再生セッション中に少なくとも 1 つのミュート状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.mute.set` |
| カウントをミュート | ビデオがミュート状態になった回数。 | メディアのクローズ | `a.media.states.mute.count` |
| 合計時間をミュート | ビデオがミュート状態であった時間（秒）。 | メディアのクローズ | `a.media.states.mute.time` |
| ピクチャーインピクチャーの影響を受けるストリーム | 再生セッション中に 1 つ以上のピクチャーインピクチャー状態が発生した場合にトリガーされます。 | メディアのクローズ | `a.media.states.pictureinpicture.set` |
| ピクチャーインピクチャーカウント | ビデオがピクチャーインピクチャー状態になった回数。 | メディアのクローズ | `a.media.states.pictureinpicture.count` |
| ピクチャーインピクチャーの合計時間 | ビデオがピクチャーインピクチャー状態であった時間（秒）。 | メディアのクローズ | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
