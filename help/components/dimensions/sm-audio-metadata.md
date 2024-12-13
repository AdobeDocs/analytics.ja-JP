---
title: ストリーミングメディアオーディオメタデータのディメンション
description: レポートスイートに対して [!UICONTROL  オーディオメタデータ ] を有効にすると、使用可能な寸法になります。
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 8%

---

# ストリーミングメディアオーディオメタデータのディメンション

ストリーミングメディア広告ディメンションは、ストリーミングメディアコレクションライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobeのストリーミングメディアコレクション]** が必要です。 詳しくは、Adobeアカウントチームにお問い合わせください。

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
