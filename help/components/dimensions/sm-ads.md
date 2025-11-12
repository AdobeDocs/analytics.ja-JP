---
title: ストリーミングメディアサービスとディメンション
description: レポートスイートに対して [!UICONTROL  メディア広告 ] を有効にした場合に使用可能なディメンション。
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# ストリーミングメディアサービスとディメンション

*このページでは、レポートスイートに対して [!UICONTROL  メディア広告 ] を有効にした場合に使用できるディメンションについて説明します。 使用可能な指標について詳しくは、[ ストリーミングメディア広告指標 ](../metrics/sm-ads.md) を参照してください。*

ストリーミングメディアサービスとディメンションは、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [ メディア広告 ](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次のディメンションを使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 広告]** | 広告の一意の ID。 | 広告開始、広告終了 | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL 広告名（変数）]** | 広告のわかりやすい名前。 類似の目的を提供する、「[!UICONTROL  広告名 ]」という名前の分類ディメンションも使用できます。 このディメンションと分類は、2 つの異なるディメンションとして扱われます。 | 広告開始、広告終了 | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL 広告プレーヤー名]** | 広告をレンダリングするプレーヤーの名前。 | 広告開始、広告終了 | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL 広告の長さ（可変）]** | ビデオ広告の長さ（秒）。 | 広告開始、広告終了 | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL 広告ポッド]** | 広告ポッドの一意の ID。 | 広告開始、広告終了 | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL ポッド位置の広告]** | 親広告ブレーク内の広告のインデックス位置（0 インデックス）。 | 広告開始、広告終了 | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL 広告主]** | 広告で取り上げた会社またはブランド。 | 広告開始、広告終了 | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL キャンペーン ID]** | 広告キャンペーンの ID | 広告開始、広告終了 | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

上記のディメンションに加えて、Adobeでは、次の分類ディメンションが自動的に作成されます。 これらのディメンションを使用するレポートを表示するには、分類データをアップロードする必要があります。

| 分類名 | 親ディメンション | 説明 |
| --- | --- | --- |
| **[!UICONTROL アセット ID]** | [[!UICONTROL コンテンツ]](sm-core.md) | メディアアセットのコンテンツの一意の ID。 例としては、TV シリーズのエピソード識別子、映画のアセット識別子、ライブイベント識別子などがあります。 これらの ID は、通常、EIDR、TMS/Gracenote、Rovi などのメタデータ認証局、または他の独自のシステムや社内システムから取得します。 |
| **[!UICONTROL コンテンツ評価]** | [[!UICONTROL コンテンツ]](sm-core.md) | テレビの保護者のガイドラインで定義されている評価。 |
| **[!UICONTROL 初回放送日]** | [[!UICONTROL コンテンツ]](sm-core.md) | コンテンツがテレビで最初に放送された日付。 この分類ディメンションは文字列なので、あらゆる日付形式を使用できます。 Adobeでは、`YYYY-MM-DD` などの一貫した日付形式を使用することをお勧めします。 |
| **[!UICONTROL 初回デジタル日]** | [[!UICONTROL コンテンツ]](sm-core.md) | コンテンツが任意のデジタルチャネルまたはプラットフォームで最初に放送された日付。 この分類ディメンションは文字列なので、あらゆる日付形式を使用できます。 Adobeでは、`YYYY-MM-DD` などの一貫した日付形式を使用することをお勧めします。 |
| **[!UICONTROL 広告長さ]** | [!UICONTROL  広告 ] | ビデオ広告の長さ（秒）。 |
| **[!UICONTROL 広告名]** | [!UICONTROL  広告 ] | 広告のわかりやすい名前。 「[!UICONTROL  広告名（変数） ]」と同等の分類です。 |
| **[!UICONTROL Creative ID]** | [!UICONTROL  広告 ] | 広告クリエイティブの ID。 |
| **[!UICONTROL ポッド名]** | [!UICONTROL  広告ポッド ] | 広告ポッドのわかりやすい名前。 |
| **[!UICONTROL ポッドの位置]** | [!UICONTROL  広告ポッド ] | コンテンツ内の広告ブレークのオフセット （秒単位）。 |
