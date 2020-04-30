---
description: 処理ルールで、コンテキストデータ変数に基づいてイベントをトリガーできます。
subtopic: Processing rules
title: コンテキストデータ変数を使用したイベントの設定
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# コンテキストデータ変数を使用したイベントの設定

処理ルールで、コンテキストデータ変数に基づいてイベントをトリガーできます。

コンテキストデータ変数は、次の形式で AppMeasurement に指定します。

```
 s.contextData['search_term']
```

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. コンテキストデータ変数名を把握しているが、現在のレポートスイートに送信していない場合、値を追加するには、変数名を入力し、「**[!UICONTROL Add variable name context data]**（‘variable name’ コンテキストデータを追加）」をクリックします。

![](assets/add-context-variable.png)

次のルール定義は、「[コンテキストデータ変数を eVar にコピー](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)」ルールを拡張し、特定のコンテキストデータ変数を含むすべてのヒットにイベントを設定します。

| ルールセット | 値 |
|---|---|
| 条件 | 「search_term」コンテキストデータが設定されている場合 |
| アクション | イベント「searches」の設定 |

次に例を示します。

![](assets/processing_rule_set_event.png)

実装のヘルプの[コンテキストデータ変数](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html)を参照してください。
