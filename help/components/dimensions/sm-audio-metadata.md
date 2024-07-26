---
title: ストリーミングメディアオーディオメタデータのディメンション
description: レポートスイートに対して [!UICONTROL  オーディオメタデータ ] を有効にすると、使用可能な寸法になります。
feature: Dimensions
source-git-commit: 45b371bd20223b86d0f17d9bdb48cffb2de15468
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 8%

---

# ストリーミングメディアオーディオメタデータのディメンション

ストリーミングメディア広告ディメンションは、ストリーミングメディアコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの分析コードを使用するには、**[!UICONTROL Adobe ストリーミング メディア コレクション アドオン]** が必要です。 詳しくは、Adobeアカウントチームにお問い合わせください。

[ メディアレポート ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) で **[!UICONTROL オーディオメタデータ]** を有効にすると、次の寸法を使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| アルバム | アルバムの名前。 | メディア開始、メディア終了 | `a.media.album` |
| 作者名 | アーティストの名前。 | メディア開始、メディア終了 | `a.media.artist` |
| 作成者 | オーディオブックの作成者の名前。 | メディア開始、メディア終了 | `a.media.author` |
| ラベル | レコードラベルの名前。 | メディア開始、メディア終了 | `a.media.label` |
| 発行者 | オーディオコンテンツパブリッシャーの名前。 | メディア開始、メディア終了 | `a.media.publisher` |
| ステーション | ラジオ局の名前または ID。 | メディア開始、メディア終了 | `a.media.station` |

{style="table-layout:auto"}
