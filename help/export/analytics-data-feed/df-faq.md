---
description: データフィードに関するよくある質問（FAQ）
keywords: Data Feed;job;pre column;post column;case sensitivity
title: データフィードに関する FAQ
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 77%

---


# データフィードに関する FAQ

データフィードに関するよくある質問（FAQ）です。

## `post_` プレフィックスのある列と `post_` プレフィックスのない列の違いは何ですか。

`post_` プレフィックスのない列には、データ収集に送信されたデータと完全に同じデータが含まれます。処理後の値は、`post_` プレフィックスの付いた列に格納されます。値を変更できる例としては、変数の持続性、処理ルール、VISTA ルール、通貨換算、その他のサーバー側ロジックが挙げられます。可能な限り、列の `post_` バージョンを使用することをお勧めします。

`post_` バージョンの区別のない列（`visit_num` など）は、post 列と見なすことができます。

## データフィードで大文字と小文字の区別を扱う方法

Adobe Analytics では、ほとんどの変数は、レポートの目的で、大文字と小文字が区別されません。例えば、「snow」、「Snow」、「SNOW」、「sNow」はすべて同じ値と見なされます。大文字と小文字の区別は、データフィードで保持されます。

非 post 列と post 列の間で同じ値の大文字と小文字の違いが見られる場合（例えば、pre 列に「snow」、post 列に「Snow」）、サイト全体で大文字と小文字の両方の値が使用されます。post 列内のバージョンは、以前に渡されて仮想 cookie に保存されている値か、同時期にそのレポートスイート用に処理された値です。

## ボットは管理コンソールのボットルールによってフィルタリングされ、データフィードに含まれますか。

データフィードには、[Admin Console ボットルール](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/bot-removal/bot-removal.html)でフィルタリングされたボットは含まれません。

## またはデータフィード列に複数の `000` 値が表示されるのはなぜで `event_list``post_event_list` すか。

一部のスプレッドシートエディタ（特にMicrosoft Excelなど）では、非常に大きな数値が自動的に丸められます。 この `event_list` 列には、カンマで区切られた多数の数字が含まれているので、Excelで大きな数字として処理されることがあります。 最後の数桁をに丸め `000`ます。

Adobeでは、Microsoft Excelで `hit_data.tsv` ファイルを自動的に開かないことをお勧めします。 代わりに、Excelの[データのインポート]ダイアログボックスを使用し、すべてのフィールドがテキストとして扱われていることを確認してください。
