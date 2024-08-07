---
title: セグメントのベストプラクティス
description: データを効率的に返す最適なセグメントを作成します。
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 100%

---

# セグメントのベストプラクティス

複雑なセグメントは、多くの場合、必要なデータを取得するために必要です。複雑なセグメントが非効率で、大きなレポートスイートで使用される場合、レポートの実行にかなり長い時間がかかります。セグメントを作成または編集する際は、次のリソースを考慮して複雑さを最小限に抑えます。

## 「次を含む」演算子のみを最後の手段として使用する

「次を含む」演算子は、セグメント化で最も処理量の多い機能の 1 つです。すべての値の内容全体を分析する必要があります。目的の値が文字列の先頭または末尾にある場合は、「次の開始」や「次の語句で終わる」などの他の演算子を使用することを検討してください。

セグメント内の「次を含む」演算子が多数の結果を返した場合、通常、レポートはタイムアウトします。例えば、`Referrer equals "."` でセグメントを作成した場合、そのセグメントはすべての値のコンテンツを検索します。代わりに、「存在する」演算子を使用することを検討してください。

## 分類を使用してディメンション項目をグループ化する

多くのセグメント条件がある場合、セグメントのパフォーマンスがすぐに低下する可能性があります。例えば、数百の異なる値で `Page equals X or Page equals Y or Page equals Z` を繰り返し使用します。これらの数百もの条件を書き出す代わりに、必要なすべての値を 1 つのセグメントに分類し、その分類された値を 1 つのセグメントで使用します。

1. 操作している変数の分類を作成します。
2. 分類テンプレートをダウンロードし、目的のスプレッドシートまたはテキストエディターで開きます。
3. セグメントに含める各ディメンション項目に同じ値を指定します。
4. 分類インポーターを使用して、スプレッドシートを Adobe Analytics にインポートし直します
5. 分類の処理が完了したら、分類された値を使用してセグメントを作成します。

この方法により、パフォーマンスが大幅に向上し、セグメント条件を簡単に変更できます。異なる値でセグメントを編集する代わりに、分類にディメンション項目を追加したり、分類からディメンション項目を削除したりできます。
