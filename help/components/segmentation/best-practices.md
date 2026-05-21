---
title: ベストプラクティス
description: セグメンテーションのベストプラクティス。
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
TQID: https://experienceleague.adobe.com/PJi-kkv6HL3jHEKArltzxMGk9BVtZ-Mr1ivHMkhxt88
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 60%

---

# セグメントのベストプラクティス

複雑なセグメントは、多くの場合、必要なデータを取得するために必要です。 複雑なセグメントが非効率で、大きなレポートスイートで使用される場合、レポートの実行にかなり長い時間がかかります。 セグメントを作成または編集する際は、次のリソースを考慮して複雑さを最小限に抑えます。

## 最後の手段として`Contains`演算子のみを使用する

[**[!UICONTROL Contains &#x200B;]**&#x200B;オペレーター](/help/components/segmentation/seg-reference/seg-operators.md)は、オペレーターがすべての値のコンテンツ全体を分析する必要があるため、セグメンテーションで最も処理集約的な機能の1つです。 目的の値が文字列の先頭または末尾にある場合は、**[!UICONTROL &#x200B;で始まる&#x200B;]**&#x200B;や&#x200B;**[!UICONTROL &#x200B;で終わる&#x200B;]**&#x200B;などの他の演算子の使用を検討してください。

セグメント内の&#x200B;**[!UICONTROL Contains]**&#x200B;演算子が多数の結果を返す場合、レポートは通常タイムアウトします。 例えば、**[!UICONTROL Referrer]** **[!UICONTROL が]** `"."`に等しいセグメントを作成した場合、セグメントはすべての値の内容を検索します。 代わりに、**[!UICONTROL Exists]**&#x200B;演算子の使用を検討してください。

## 分類を使用してディメンション項目をグループ化する

多くのセグメント条件がある場合、セグメントのパフォーマンスがすぐに低下する可能性があります。 例えば、**[!UICONTROL Page]** **[!UICONTROL equals]** `X` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Y` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Z`が数百の異なる値で繰り返されます。 これらの数百もの条件を書き出す代わりに、必要なすべての値を 1 つのセグメントに分類し、その分類された値を 1 つのセグメントで使用します。

1. 操作している変数の分類を作成します。
2. 分類テンプレートをダウンロードし、目的のスプレッドシートまたはテキストエディターで開きます。
3. セグメントに含める各ディメンション項目に同じ値を指定します。
4. 分類インポーターを使用して、スプレッドシートを Adobe Analytics にインポートし直します
5. 分類の処理が完了したら、分類された値を使用してセグメントを作成します。

この方法により、パフォーマンスが大幅に向上し、セグメント条件を簡単に変更できます。 異なる値でセグメントを編集する代わりに、分類にディメンション項目を追加したり、分類からディメンション項目を削除したりできます。
