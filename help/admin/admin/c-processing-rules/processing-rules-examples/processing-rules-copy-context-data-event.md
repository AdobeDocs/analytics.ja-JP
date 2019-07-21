---
description: 処理ルールで、コンテキストデータ変数に基づいてイベントをトリガーできます。
seo-description: 処理ルールで、コンテキストデータ変数に基づいてイベントをトリガーできます。
seo-title: コンテキストデータ変数を使用したイベントの設定
solution: Analytics
subtopic: 処理ルール
title: コンテキストデータ変数を使用したイベントの設定
topic: 管理ツール
uuid: 4a6018eb-03e2-4ec8-874b- e48bf716e103
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# コンテキストデータ変数を使用したイベントの設定

処理ルールで、コンテキストデータ変数に基づいてイベントをトリガーできます。

コンテキストデータ変数は、次の形式で AppMeasurement に指定します。

```
 s.contextData['search_term']
```

[!UICONTROL コンテキスト変数]リストには、過去 30 日間にレポートスイートへ送信されたすべての変数が含まれます。If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

The following rule definition expands on the [Copy a Context Data Variable to an eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) rule to also set an event on every hit that contains a specific context data variable:

| ルールセット | 値 |
|---|---|
| 条件 | 「search_term」コンテキストデータが設定されている場合 |
| アクション | イベント「searches」の設定 |

次に例を示します。

![](assets/processing_rule_set_event.png)

実装のヘルプの[コンテキストデータ変数](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables)を参照してください。
