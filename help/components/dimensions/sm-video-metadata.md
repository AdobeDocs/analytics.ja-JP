---
title: ストリーミングメディアビデオのメタデータディメンション
description: レポートスイートに対して [!UICONTROL  ビデオメタデータ ] を有効にすると、使用可能なディメンションになります。
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 7%

---

# ストリーミングメディアビデオのメタデータディメンション

*このページでは、レポートスイートに対して [!UICONTROL  ビデオメタデータ ] を有効にした場合に使用可能なディメンションについて説明します。 使用可能な指標については、[ ストリーミングメディアビデオメタデータ指標 ](../metrics/sm-video-metadata.md) を参照してください。*

ストリーミングメディア広告ディメンションは、ストリーミングメディアコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの分析コードを使用するには、**[!UICONTROL Adobe ストリーミング メディア コレクション アドオン]** が必要です。 詳しくは、Adobeアカウントチームにお問い合わせください。

[ メディアレポート ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) の **[!UICONTROL ビデオメタデータ]** を有効にすると、次のディメンションを使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| 広告の読み込み | 読み込まれた広告のタイプ。 | 未定 | `a.media.adLoad` |
| 日パート | コンテンツが放送または再生された時間。 任意の文字列値がサポートされています。 | メディア開始、メディア終了 | `a.media.dayPart` |
| エピソード | エピソード番号。 | メディア開始、メディア終了 | `a.media.episode` |
| メディアフィードのタイプ | フィードのタイプ。 | メディア開始、メディア終了 | `a.media.feed` |
| ジャンル | コンテンツプロデューサーによって定義されたコンテンツのタイプまたはグループ。 このディメンションでは、コンマで区切られた複数の値がサポートされています。 | メディア開始、メディア終了 | `a.media.genre` |
| MVPD | Adobe認証によって提供される MVPD。 | メディア開始、メディア終了 | `a.media.pass.mvpd` |
| ネットワーク | ネットワーク名またはチャネル名 | メディア開始、メディア終了 | `a.media.network` |
| シーズン | 番組が属するシーズン番号。 | メディア開始、メディア終了 | `a.media.season` |
| 番組 | プログラムまたはシリーズの名前。 | メディア開始、メディア終了 | `a.media.show` |
| 番組タイプ | コンテンツのタイプを表す整数。<br>`0`：完全なエピソード <br>`1`：プレビューまたは予告編 <br>`2`：クリップ <br>`3`：その他 | メディア開始、メディア終了 | `a.media.type` |

{style="table-layout:auto"}