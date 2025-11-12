---
title: ストリーミングメディアチャプターディメンション
description: レポートスイートに対して [!UICONTROL  メディアチャプター ] を有効にした場合に使用可能なディメンション。
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 8%

---

# ストリーミングメディアサービスチャプターディメンション

*このページでは、レポートスイートに対して [!UICONTROL  メディアチャプター ] を有効にした場合に使用可能なディメンションについて説明します。 使用可能な指標については、[ ストリーミングメディアサービスのチャプター指標 ](../metrics/sm-chapters.md) を参照してください。*

ストリーミングメディアサービスチャプターディメンションは、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の下の [ メディアチャプター ](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次のディメンションを使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 第]** 章 | 自動生成されたチャプター ID。 | チャプタークローズ | `a.media.chapter.name` | `xdm.mediaReporting.`<br>`chapterDetails.ID` |

上記のディメンションに加えて、Adobeでは、次の分類ディメンションが自動的に作成されます。 これらのディメンションを使用するレポートを表示するには、分類データをアップロードする必要があります。

| 分類名 | 親ディメンション | 説明 |
| --- | --- | --- |
| **[!UICONTROL 作成者]** | [[!UICONTROL コンテンツ]](sm-core.md) | コンテンツの作成者。 |
| **[!UICONTROL チャプター長]** | [!UICONTROL  第 ] 章 | チャプターの長さ（秒）。 |
| **[!UICONTROL チャプター名]** | [!UICONTROL  第 ] 章 | チャプターのわかりやすい名前。 |
| **[!UICONTROL チャプターオフセット]** | [!UICONTROL  第 ] 章 | 開始時からのコンテンツ内のチャプターのオフセット （秒）。 |
| **[!UICONTROL チャプター位置]** | [!UICONTROL  第 ] 章 | コンテンツ内のチャプターのインデックス位置。 |
