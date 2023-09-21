---
title: ボット名
description: ボットルールに一致したボットの名前。
exl-id: 668c1dce-c603-477a-9df7-dacb649bbf63
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# ボット名

「ボット名」 [ディメンション](overview.md) は、次を使用して検出されたボットの名前を示します： [ボットルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). これらのルールは、デフォルトの IAB ルールや、組織が設定するカスタムボットルールにすることができます。 サイトを訪問しているボットや最もトラフィックを生み出しているボットの詳細を知りたい場合に役立ちます。

一致するヒット数 [!UICONTROL ボットルール] は、このディメンションを除く、すべての Analytics レポートから自動的に除外されます。 [ボットの発生件数](../metrics/bot-occurrences.md)、および [ボットページビュー数](../metrics/bot-page-views.md). このディメンションとこれら 2 つの指標を使用して、残りのレポートから除外されるボットデータを確認できます。

ボットレポートは他のレポートスイートデータとは別になっているので、このディメンションでは次のディメンションと指標のみがサポートされます。

* [ページ](page.md)
* 時間ベースのディメンション ( 例： [日](day.md), [週](week.md)または [月](month.md))
* [ボットの発生件数](../metrics/bot-occurrences.md)
* [ボットページビュー数](../metrics/bot-page-views.md)

このディメンションで他のディメンションまたは指標を使用しても、データは返されません。

## このディメンションへのデータ入力

を有効にしている場合 [ボットルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)を指定すると、このディメンションは自動的にデータを収集します。 まだを有効にしていない場合は、 [!UICONTROL ボットルール]の場合、このディメンションはAnalysis Workspaceには表示されません。

## ディメンション項目

各ディメンション項目は、IAB またはカスタムボットルール条件に一致したボットの名前をリストします。
