---
title: 音声分析指標
description: 音声分析指標
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 21%

---

# 音声分析指標

[!UICONTROL &#x200B; アプリケーションレポート &#x200B;] で [[!UICONTROL &#x200B; 音声およびチャットボット &#x200B;]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md) を有効にすると、次の指標（および [&#x200B; ディメンション &#x200B;](../dimensions/voice-dimensions.md)）が作成されます。 [&#x200B; コンテキストデータ変数 &#x200B;](/help/implement/vars/page-vars/contextdata.md) を使用して、値を `1` （該当する場合は複数）に設定できます。 レポートスイートの設定で有効にすると、音声分析指標を関連するコンテキストデータ変数にマッピングする [&#x200B; 処理ルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) が自動的に作成されます。

| Metric name | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| 音声発話 | 音声アシスタントに対してコマンドが発行されたときのトリガーです。 | `a.voiceutterances` |
| 音声終了セッション | 音声アプリが閉じられたときのトリガー。 | `a.voiceendsession` |
| 音声エラー | 音声アプリでエラーが発生した場合のトリガー。 | `a.voiceerror` |

{style="table-layout:auto"}
