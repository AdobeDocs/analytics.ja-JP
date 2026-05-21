---
title: インスタンス
description: 変数が設定された（持続的でない）ヒット数。
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
TQID: https://experienceleague.adobe.com/a6Ycw6CVzeSKuOCHezQtLNIZZo6vbkVneVWO0C2QfxQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 263
ht-degree: 50%

---

# インスタンス

「インスタンス」 [指標](overview.md)は、イメージリクエストでディメンションが明示的に定義された回数を示します。 [eVars](../dimensions/evar.md)などのディメンションには、設定されたヒットを超えたディメンション項目が保持されるものもあります。 この指標は、その値が持続するヒットなしでディメンション項目が設定された回数を確認する必要がある場合に役立ちます。

## この指標の計算方法

レポートスイート内のすべてのヒットのうち、イメージリクエストにディメンション項目を明示的に設定するヒットのみを含めます。 [eVars](../dimensions/evar.md)などのディメンションは、設定されたヒットの後も保持される場合があります。 [ページビュー](page-views.md)や[発生件数](occurrences.md)などの指標は、初期値と持続値の両方をカウントします。 この指標では、持続値はカウントされません。

例えば、訪問者が自社サイトを訪問し、内部検索を利用したとします。 EVar1で内部検索を追跡します。 一度内部検索を使用すると、ページをさらに5 ページ閲覧してから検索に進みます。

Workspaceでレポートを表示すると、1つのeVar1 インスタンスと6つのインスタンスが表示されます。 1つのインスタンスは検索結果ページでカウントされますが、オカレンス指標は初期値とその後の永続値をカウントします。

## 類似の指標と比較

* **インスタンスと[発生回数](occurrences.md)**：ディメンション項目が保持されるヒットはインスタンスに含まれません。 発生回数は、ディメンション項目が設定または保持されたヒット数です。
* **インスタンス対[&#x200B; ページビュー](page-views.md)**: インスタンスには、ページビュートラッキング呼び出し（[`t()`](/help/implement/vars/functions/t-method.md)）、リンクトラッキング呼び出し（[`tl()`](/help/implement/vars/functions/tl-method.md)）、概要[&#x200B; データソース &#x200B;](/help/import/data-sources/overview.md)からのデータなど、すべてのヒットタイプが含まれます。 ページビュー数指標には、リンクトラッキングコールおよび概要データソースを除く、ページビュートラッキングコールのみが含まれます。
