---
title: 音声分析指標
description: 音声分析指標
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: 6a229439c455389b88d5fe96a0366b8888809c02
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 21%

---

# 音声分析指標

[[!UICONTROL  アプリケーションレポート ]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md) で [!UICONTROL  音声およびチャットボット ] を有効にすると、次の指標（および [ ディメンション ](../dimensions/voice-dimensions.md)）が作成されます。 [ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md) を使用して、値を `1` （該当する場合は複数）に設定できます。 レポートスイートの設定で有効にすると、音声分析指標を関連するコンテキストデータ変数にマッピングする [ 処理ルール ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) が自動的に作成されます。

| Metric name | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| 音声発話 | 音声アシスタントに対してコマンドが発行されたときのトリガーです。 | `a.voiceutterances` |
| 音声終了セッション | 音声アプリが閉じられたときのトリガー。 | `a.voiceendsession` |
| 音声エラー | 音声アプリでエラーが発生した場合のトリガー。 | `a.voiceerror` |

{style="table-layout:auto"}
