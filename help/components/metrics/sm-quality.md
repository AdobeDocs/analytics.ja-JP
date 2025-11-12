---
title: ストリーミングメディアサービス品質指標
description: レポートスイートの [!UICONTROL &#x200B; メディア品質 &#x200B;] を有効にするときに使用できる指標です。
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 2%

---

# ストリーミングメディアサービス品質指標

*このページでは、レポートスイートに対して [!UICONTROL &#x200B; メディア品質 &#x200B;] を有効にした場合に使用可能な指標について説明します。 使用可能なディメンションについては、[&#x200B; ストリーミングメディアサービス品質ディメンション &#x200B;](../dimensions/sm-quality.md) を参照してください。*

ストリーミングメディアサービス品質指標は、ストリーミングメディアサービスライブラリを介したデータ収集に対する追加のレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [&#x200B; メディア品質 &#x200B;](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 平均ビットレート]** | 再生セッションの再生時間に対するすべてのビットレート値の加重平均。 | メディアのクローズ | `a.media.qoe.`<br>`bitrateAverage` | `xdm.mediaReporting.`<br>`qoeDataDetails.bitrateAverage` |
| **[!UICONTROL ビットレート変更の影響を受けたストリーム]** | 再生セッション中にビットレートが 1 回以上変更された場合にトリガーとなるブール値。 | メディアのクローズ | `a.media.qoe.`<br>`bitrateChange` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBitrateChangeImpactedStreams` |
| **[!UICONTROL ビットレートの変更]** | ビットレートが変更された回数。 | メディアのクローズ | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL バッファーの影響を受けたストリーム]** | ビデオが少なくとも 1 回はバッファステートに入った場合にトリガーにするブール値です。 | メディアのクローズ | `a.media.qoe.`<br>`buffer` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBufferImpactedStreams` |
| **[!UICONTROL バッファーイベント]** | 再生セッション中にビデオがバッファリングされた回数。 | メディアのクローズ | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferCount` |
| **[!UICONTROL 合計バッファー時間]** | ビデオがすべてのバッファーイベントでバッファリングに費やした時間（秒単位）。 | メディアのクローズ | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferTime` |
| **[!UICONTROL 開始前にドロップ]** | ビデオのメインコンテンツが開始される前にユーザーが終了した場合にトリガーにするブール値です。 | メディアのクローズ | `a.media.qoe.`<br>`dropBeforeStart` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`isDroppedBeforeStart` |
| **[!UICONTROL ドロップフレーム]** | 再生セッション中にドロップされたフレームの合計数を表す整数。 | メディアのクローズ | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.droppedFrames` |
| **[!UICONTROL ドロップフレームの影響を受けたストリーム]** | 再生セッション中にフレームがドロップされた場合にトリガーを設定するブール値。 | メディアのクローズ | `a.media.qoe.`<br>`droppedFrames` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasDroppedFrameImpactedStreams` |
| **[!UICONTROL エラーの影響を受けたストリーム]** | 再生セッション中にビデオでエラーが発生した場合にトリガーにするブール値。 | メディアのクローズ | `a.media.qoe.`<br>`error` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasErrorImpactedStreams` |
| **[!UICONTROL エラーイベント]** | 再生セッション中に発生したエラーの合計数を表す整数。 | メディアのクローズ | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.errorCount` |
| **[!UICONTROL 開始時間]** | ビデオの開始に要した時間（ミリ秒単位）。 Adobeは、この値を秒単位で変換して保存します。 | メディアのクローズ | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.timeToStart` |
