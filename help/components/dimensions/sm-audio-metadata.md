---
title: ストリーミングメディアサービスのオーディオメタデータのディメンション
description: レポートスイートに対して [!UICONTROL &#x200B; オーディオメタデータ &#x200B;] を有効にすると、使用可能な寸法になります。
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 8%

---

# ストリーミングメディアサービスのオーディオメタデータのディメンション

ストリーミングメディアサービスとディメンションは、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobe Analytics for Streaming Media Ad-on]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** で [ オーディオメタデータ ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) を有効にすると、次の寸法を使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 |
| --- | --- | --- | --- |
| アルバム | アルバムの名前。 | メディア開始、メディア終了 | `a.media.album` |
| 作者名 | アーティストの名前。 | メディア開始、メディア終了 | `a.media.artist` |
| 作成者 | オーディオブックの作成者の名前。 | メディア開始、メディア終了 | `a.media.author` |
| ラベル | レコードラベルの名前。 | メディア開始、メディア終了 | `a.media.label` |
| 発行者 | オーディオコンテンツパブリッシャーの名前。 | メディア開始、メディア終了 | `a.media.publisher` |
| ステーション | ラジオ局の名前または ID。 | メディア開始、メディア終了 | `a.media.station` |

{style="table-layout:auto"}
