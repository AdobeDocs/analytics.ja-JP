---
title: ストリーミングメディアサービス品質ディメンション
description: レポートスイートに対して [!UICONTROL &#x200B; メディア品質 &#x200B;] を有効にした場合に使用可能なディメンション。
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# ストリーミングメディアサービス品質ディメンション

*このページでは、レポートスイートに対して [!UICONTROL &#x200B; メディア品質 &#x200B;] を有効にした場合に使用可能なディメンションについて説明します。 使用可能な指標について詳しくは、[&#x200B; ストリーミングメディアサービス品質指標 &#x200B;](../metrics/sm-quality.md) を参照してください。*

ストリーミングメディアサービス品質ディメンションは、訪問者が消費するコンテンツの品質に関するレポートを提供します。 これらのディメンションを使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [&#x200B; メディア品質 &#x200B;](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次のディメンションを使用できます。

| ディメンション名 | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 平均ビットレート]** | 平均ビットレート（100 KBPS バケット間隔）。 これは、特定の再生セッションの再生時間に関するすべてのビットレート値の加重平均として計算されます。 | メディアのクローズ | `a.media.qoe.`<br>`bitrateAverageBucket` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrate`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateAverageBucket` |
| **[!UICONTROL ビットレートの変更]** | 再生セッション中に発生したビットレート変更の数。 | メディアのクローズ | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL バッファーイベント]** | 再生セッション中にメディアプレーヤーがバッファー状態に入った回数。 | メディアのクローズ | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferCount` |
| **[!UICONTROL 合計バッファー時間]** | バッファーに費やした合計時間（秒）。 | メディアのクローズ | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferTime` |
| **[!UICONTROL ドロップフレーム]** | 再生セッション中に発生したドロップフレームの合計数。 | メディアのクローズ | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`droppedFrames` |
| **[!UICONTROL エラー]** | 再生セッション中に発生したエラーの合計数。 | メディアのクローズ | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`errorCount` |
| **[!UICONTROL 外部エラー ID]** | CDN エラーなど、外部ソースからのすべての一意のエラー ID。 目的のエラーコードまたは ID を指定する必要があります。 複数のエラー ID を使用できます。 | メディアのクローズ | `a.media.qoe.`<br>`externalErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`externalErrors` |
| **[!UICONTROL Player SDKのエラー ID]** | コンテンツプレイヤーのSDKによって生成されるすべての一意のエラー ID。 目的のエラーコードまたは ID を指定する必要があります。 複数のエラー ID を使用できます。 | メディアのクローズ | `a.media.qoe.`<br>`playerSdkErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`playerSdkErrors` |
| **[!UICONTROL 開始時間]** | QoSObject を使用して設定しない場合、この値はデフォルトで `0` になります。 値をミリ秒単位で設定します。 Analysis Workspaceは、このディメンションを秒単位でレポートします。 | メディア開始、メディア終了 | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`timeToStart` |
