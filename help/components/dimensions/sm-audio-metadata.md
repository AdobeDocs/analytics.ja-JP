---
title: ストリーミングメディアサービスのオーディオメタデータのディメンション
description: レポートスイートに対して [!UICONTROL &#x200B; オーディオメタデータ &#x200B;] を有効にすると、使用可能な寸法になります。
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 6%

---

# ストリーミングメディアサービスのオーディオメタデータのディメンション

ストリーミングメディアサービスとディメンションは、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** で [&#x200B; オーディオメタデータ &#x200B;](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の寸法を使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL アルバム]** | アルバムの名前。 | メディア開始、メディア終了 | `a.media.album` | `xdm.mediaCollection.`<br>`sessionDetails.album`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.album` |
| **[!UICONTROL アーティスト]** | アーティストの名前。 | メディア開始、メディア終了 | `a.media.artist` | `xdm.mediaCollection.`<br>`sessionDetails.artist`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.artist` |
| **[!UICONTROL 作成者]** | オーディオブックの作成者の名前。 | メディア開始、メディア終了 | `a.media.author` | `xdm.mediaCollection.`<br>`sessionDetails.author`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.author` |
| **[!UICONTROL ラベル]** | レコードラベルの名前。 | メディア開始、メディア終了 | `a.media.label` | `xdm.mediaCollection.`<br>`sessionDetails.label`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.label` |
| **[!UICONTROL 発行者]** | オーディオコンテンツパブリッシャーの名前。 | メディア開始、メディア終了 | `a.media.publisher` | `xdm.mediaCollection.`<br>`sessionDetails.publisher`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.publisher` |
| **[!UICONTROL 測点]** | ラジオ局の名前または ID。 | メディア開始、メディア終了 | `a.media.station` | `xdm.mediaCollection.`<br>`sessionDetails.station`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.station` |
