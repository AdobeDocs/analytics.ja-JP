---
title: ストリーミングメディアサービスのコアディメンション
description: レポートスイートの [!UICONTROL Media Core] を有効にするときに使用できるディメンションです。
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 7%

---

# ストリーミングメディアサービスのコアディメンション

*このページでは、レポートスイートに対して [!UICONTROL Media Core] を有効にしたときに使用できるディメンションについて説明します。 使用可能な指標について詳しくは、[ ストリーミングメディアサービスのコア指標 ](../metrics/sm-core.md) を参照してください。*

ストリーミングメディアサービスのコアディメンションは、ストリーミングメディアサービスライブラリを通じて収集されたデータに対して基本的なレポート機能を提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [Media Core](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次のディメンションを使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL コンテンツ]** | コンテンツのコンテンツ ID。 | メディア開始、メディア終了 | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL コンテンツチャネル]** | コンテンツが再生される配信ステーションまたはチャネル。 任意の文字列値が有効です。 | メディア開始、メディア終了 | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL コンテンツの長さ（可変）]** | 消費されるコンテンツの最大長（またはデュレーション） （秒単位）。 このディメンションは、「[!UICONTROL  分平均オーディエンス ]」を含む複数の指標に対して必要です。 このディメンションが設定されていない場合、依存指標は使用できません。<br><br> 同様の目的を提供する、「[!UICONTROL  ビデオの長さ ]」という名前の分類ディメンションも使用できます。 このディメンションと分類は、2 つの異なるディメンションとして扱われます。 | メディア開始、メディア終了 | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL コンテンツ名（変数）]** | コンテンツのわかりやすい名前。 同様の目的を提供する、「[!UICONTROL  ビデオ名 ]」という分類も使用できます。 このディメンションと分類は、2 つの異なるディメンションとして扱われます。 | メディア開始、メディア終了 | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL コンテンツプレーヤー名]** | コンテンツプレイヤーの名前。 | メディア開始、メディア終了 | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL コンテンツセグメント]** | 表示されたコンテンツの部分を表す間隔（分）。 セグメントは、再生セッション中の再生ヘッドの値の最小値および最大値として計算されます。 | メディアのクローズ | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL コンテンツタイプ]** | コンテンツのタイプ。 有効な値には、`song`、`podcast`、`audiobook`、`radio`、`VoD`、`Live`、`Linear`、`UGC`、`DVoD`、カスタム値などがあります。 | メディア開始、メディア終了 | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL メディアパス]** | 訪問者がコンテンツに到達するまでにかかったパス。 | メディア開始 | `a.media.path` | |
| **[!UICONTROL ストリームタイプ]** | ストリームタイプ。 有効な値には、`audio` および `video` などがあります。 | メディア開始、メディア終了 | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

上記のディメンションに加えて、Adobeでは、次の分類ディメンションが自動的に作成されます。 これらのディメンションを使用するレポートを表示するには、分類データをアップロードする必要があります。

| 分類名 | 親ディメンション | 説明 |
| --- | --- | --- |
| **[!UICONTROL ビデオ長]** | [!UICONTROL コンテンツ] | 消費されるコンテンツの最大長（またはデュレーション） （秒単位）。 コンテンツの長さに依存する指標ではこの分類を使用できません。この分類を使用して「[!UICONTROL  分平均オーディエンス ]」などの指標を取得するには、計算指標を作成する必要があります。 |
| **[!UICONTROL ビデオ名]** | [!UICONTROL コンテンツ] | コンテンツのわかりやすい名前。 「[!UICONTROL  コンテンツ名（変数） ]」の分類同等です。 |
