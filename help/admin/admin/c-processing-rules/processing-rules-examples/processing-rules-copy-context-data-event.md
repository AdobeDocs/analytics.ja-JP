---
description: 処理ルールで、コンテキストデータ変数に基づいてイベントをトリガーできます。
subtopic: Processing rules
title: コンテキストデータ変数を使用したイベントの設定
feature: Admin Tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 100%

---

# コンテキストデータ変数を使用したイベントの設定

処理ルールで、コンテキストデータ変数に基づいてイベントをトリガーできます。

コンテキストデータ変数は、次の形式で AppMeasurement に指定します。

```
 s.contextData['search_term']
```

[!UICONTROL コンテキスト変数]リストには、過去 30 日間にレポートスイートへ送信されたすべての変数が含まれます。コンテキストデータ変数名を把握しているが、現在のレポートスイートに送信していない場合、値を追加するには、変数名を入力して、「**[!UICONTROL 変数名コンテキストデータを追加]**」をクリックします。

![](assets/add-context-variable.png)

次のルール定義は、「[コンテキストデータ変数を eVar にコピー](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)」ルールを拡張し、特定のコンテキストデータ変数を含むすべてのヒットにイベントを設定します。

| ルールセット | 値 |
|---|---|
| 条件 | 「search_term」コンテキストデータが設定されている場合 |
| アクション | イベント「searches」の設定 |

次に例を示します。

![](assets/processing_rule_set_event.png)

実装のヘルプの[コンテキストデータ変数](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/page-vars/contextdata.html)を参照してください。
