---
title: ストリーミングメディアサービスのビデオメタデータのディメンション
description: レポートスイートに対して [!UICONTROL  ビデオメタデータ ] を有効にすると、使用可能なディメンションになります。
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 3%

---

# ストリーミングメディアサービスのビデオメタデータのディメンション

*このページでは、レポートスイートに対して [!UICONTROL  ビデオメタデータ ] を有効にした場合に使用可能なディメンションについて説明します。 使用可能な指標については、[ ストリーミングメディアサービスのビデオメタデータ指標 ](../metrics/sm-video-metadata.md) を参照してください。*

ストリーミングメディアサービスとディメンションは、ストリーミングメディアサービスコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [ ビデオメタデータ ](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次のディメンションを使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 広告読み込み]** | 読み込まれた広告のタイプ。 | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL 日分割]** | コンテンツが放送または再生された時間。 任意の文字列値がサポートされています。 | メディア開始、メディア終了 | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL エピソード]** | エピソード番号。 | メディア開始、メディア終了 | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL メディアフィードのタイプ]** | フィードのタイプ。 | メディア開始、メディア終了 | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL ジャンル]** | コンテンツプロデューサーによって定義されたコンテンツのタイプまたはグループ。 このディメンションでは、コンマで区切られた複数の値がサポートされています。 | メディア開始、メディア終了 | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | Adobe認証で提供されるMVPD。 | メディア開始、メディア終了 | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL ネットワーク]** | ネットワーク名またはチャネル名。 | メディア開始、メディア終了 | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL シーズン]** | 番組が属するシーズン番号。 | メディア開始、メディア終了 | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL 表示]** | プログラムまたはシリーズの名前。 | メディア開始、メディア終了 | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL 表示タイプ]** | コンテンツのタイプを表す整数。<br>`0`：完全なエピソード <br>`1`：プレビューまたは予告編 <br>`2`：クリップ <br>`3`：その他 | メディア開始、メディア終了 | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

