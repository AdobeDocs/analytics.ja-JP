---
description: 処理ルールは、コンテキストデータ変数の値を prop および eVar に移動するために使用されます。
seo-description: 処理ルールは、コンテキストデータ変数の値を prop および eVar に移動するために使用されます。
seo-title: コンテキストデータ変数のeVarへのコピー
solution: Analytics
subtopic: 処理ルール
title: コンテキストデータ変数のeVarへのコピー
topic: 管理ツール
uuid: 1bebas4c-71e9-49ce- b154-78408cc532a3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# コンテキストデータ変数のeVarへのコピー

処理ルールは、コンテキストデータ変数の値を prop および eVar に移動するために使用されます。

コンテキストデータ変数は、次の形式で AppMeasurement に指定します。

```
 s.contextData['search_term']
```

[!UICONTROL コンテキスト変数]リストには、過去 30 日間にレポートスイートへ送信されたすべての変数が含まれます。If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

次のルール定義では、すべてのヒットで、特定のコンテキストデータ変数を含む eVar が設定されます。

| ルールセット | 値 |
|---|---|
| 条件 | 「search_term」コンテキストデータが設定されている場合 |
| アクション | eVar3 の値を上書きして「search_term」に設定する |

次に例を示します。

![](assets/set-context-data.png)

実装のヘルプの[コンテキストデータ変数](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables)を参照してください。
