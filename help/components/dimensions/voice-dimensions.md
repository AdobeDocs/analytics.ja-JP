---
title: 音声分析のディメンション
description: 音声分析のディメンション
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 133
ht-degree: 16%

---

# 音声分析のディメンション

[[!UICONTROL &#x200B; アプリケーションレポート &#x200B;]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md)で[!UICONTROL 音声とチャットボット &#x200B;]を有効にすると、次のディメンション（および[指標](../metrics/voice-metrics.md)）が作成されます。 [&#x200B; コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)を使用して、目的の文字列値に設定できます。 レポートスイート設定で有効にすると、音声分析ディメンションを関連するコンテキストデータ変数にマッピングする[処理ルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)が自動的に作成されます。

| ディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| ボイスエラータイプ | 発生したエラーのタイプ。 | `a.voiceerrortype` |
| ボイス言語 | ユーザーが音声アプリで操作する言語。 | `a.voicelanguage` |
| ボイスインテント | ユーザーが実行するコマンド。 | `a.voiceintent` |
| ボイスアプリの応答 | 音声アプリがユーザーに返した応答。 | `a.voiceappresponse` |
| ボイス認証 | 音声アプリを操作する際のユーザーの認証状態。 | `a.voiceauthentication` |
| 目標地点 ID | POI ID。 | `a.loc.poi.id` |

{style="table-layout:auto"}
