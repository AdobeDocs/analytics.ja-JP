---
title: 音声分析指標
description: 音声分析指標
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 102
ht-degree: 21%

---

# 音声分析指標

[[!UICONTROL  アプリケーションレポート ]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md)で[!UICONTROL 音声とチャットボット ]を有効にすると、次の指標（および[ ディメンション ](../dimensions/voice-dimensions.md)）が作成されます。 [ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)を使用して、値`1` （または該当する場合はそれ以上）に設定できます。 レポートスイートの設定で有効にすると、音声分析の指標を関連するコンテキストデータ変数にマッピングする[処理ルール ](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)が自動的に作成されます。

| Metric name | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| 音声発話 | 音声アシスタントにコマンドが発行されたときのトリガー。 | `a.voiceutterances` |
| 音声終了セッション | 音声アプリが閉じられた際のトリガー。 | `a.voiceendsession` |
| 音声エラー | 音声アプリでエラーが発生した場合のトリガー。 | `a.voiceerror` |

{style="table-layout:auto"}
