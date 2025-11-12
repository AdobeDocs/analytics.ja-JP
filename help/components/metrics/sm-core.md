---
title: ストリーミングメディアサービスのコア指標
description: レポートスイートの [!UICONTROL Media Core] を有効にするときに使用できる指標です。
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---

# ストリーミングメディアサービスのコア指標

*このページでは、レポートスイートに対して [!UICONTROL Media Core] を有効にしたときに使用可能な指標について説明します。 使用可能なディメンションについては、[&#x200B; ストリーミングメディアサービスのコアディメンション &#x200B;](../dimensions/sm-core.md) を参照してください。*

ストリーミングメディアサービスのコア指標は、ストリーミングメディアサービス収集ライブラリを介して収集されたデータに対して基本的なレポート機能を提供します。 これらの指標を使用するには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]** が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

**[!UICONTROL メディアレポート]** の [Media Core](/help/admin/tools/manage-rs/edit-settings/media-management.md) を有効にすると、次の指標を使用できます。

| Metric name | 説明 | 次を使用して送信 | コンテキストデータ変数 | XDM フィールド |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 分平均オーディエンス]** | コンテンツの特定の部分に費やした合計時間を、すべての再生セッションの長さで割った値。<br>`[Time spent] / [Media length]` | メディアのクローズ | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL コンテンツ完了]** | コンテンツの一部が完了したときに発生するトリガー。 この指標は、必ずしもコンテンツ全体を表示したことを意味するものではなく、先にスキップした可能性があります。 コンテンツの最後に到達しただけです。 | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL 一時停止された影響を受けたストリーム]** | コンテンツの再生中に 1 つ以上の一時停止が発生した場合にトリガーを設定するブール値。 | メディアのクローズ | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL 一時停止イベント]** | 再生セッション中に発生した一時停止の数。 | メディアのクローズ | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL 合計一時停止時間]** | すべての一時停止イベントの合計時間（秒単位）。 | メディアのクローズ | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL コンテンツ開始]** | メディアの最初のフレームが消費されます。 広告中またはバッファー中にユーザーが削除された場合、このイベントはトリガーになりません。 | メディアのクローズ | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL 10% プログレスマーカー &#x200B;]**<br>**[!UICONTROL 25% プログレスマーカー &#x200B;]**<br>**[!UICONTROL 50% プログレスマーカー &#x200B;]**<br>**[!UICONTROL 75% プログレスマーカー &#x200B;]**<br>**[!UICONTROL 95% プログレスマーカー]** | 再生ヘッドは、長さに基づいてコンテンツの指示されたマーカーを通過する。 巻き戻しをシークした場合でも、各マーカーは 1 回だけカウントされます。 早送りシークの場合、スキップされたマーカーはカウントされません。 | メディアのクローズ | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL コンテンツ再開]** | 30 分を超えるバッファー、一時停止、または停止期間の後にコンテンツが再開された場合にトリガーとなるブール値。 また、VideoInfo trackPlay でプレイヤーによって設定された場合のトリガー。 | メディアのクローズ | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL コンテンツセグメント表示]** | 表示されたセグメントの最初のフレームをトリガーにするブール値。 | メディアのクローズ | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL メディア開始]** | メディアが最初に読み込まれたときにトリガーを付けるブール値です。 このイベントには、広告、バッファリング、エラーが含まれます。 | メディア開始 | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL コンテンツに費やした時間]** | メインコンテンツで再生タイプのすべてのイベントの合計イベント時間（秒単位）。 | メディアのクローズ | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL ユニーク再生時間]** | 一意のコンテンツが再生された合計時間（秒単位）。 この指標は、コンテンツの繰り返し表示時の再生時間（例：巻き戻しのシーク）を除外します。 | メディアのクローズ | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
