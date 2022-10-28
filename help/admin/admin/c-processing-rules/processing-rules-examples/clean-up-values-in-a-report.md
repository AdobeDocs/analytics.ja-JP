---
description: 値が一般的な誤ったつづりと一致する場合、レポート内で正しく表示されるように更新することができます。
subtopic: Processing rules
title: レポート内の値のクリーンアップ
feature: Admin Tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 84%

---

# レポート内の値のクリーンアップ

値が一般的な誤ったつづりと一致する場合、レポート内で正しく表示されるように更新することができます。

誤って他の値と一致しないようにするには、使用可能な最も厳しい一致オプションを使用します。 変数（下の例では prop1）に対してレポートを実行し、置換するように選択した語句を検索して、意図しない値と一致しないようにすることができます。文字列の比較では大文字と小文字が区別されます。

| ルールセット | 値 |
|---|---|
| 条件 | prop1 が Shoping で始まる場合 |
| アクション | prop1 の値を上書きしてカスタム値 Shopping に設定する |

次に例を示します。

![](assets/clean-up-values-in-report.png)
