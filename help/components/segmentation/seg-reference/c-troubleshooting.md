---
description: セグメントに関連する問題のトラブルシューティングと解決方法について説明します。
title: トラブルシューティング
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
TQID: https://experienceleague.adobe.com/-9XPy2cFezGBFnygKW4gbHG2zuNBfn5Z29InEDF58ZM
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
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 1%

---

# トラブルシューティング

この記事では、セグメントに関する一般的な問題と、これらの問題のトラブルシューティング方法について説明します。

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## セグメントがデータを全く返さないのはなぜですか？ {#no-data}

考えられる理由：

* 逆ネスト – 例えば、![訪問](/help/assets/icons/Visit.svg) **[!UICONTROL 訪問]** コンテナの下に![&#x200B; ユーザー](/help/assets/icons/User.svg) **[!UICONTROL 訪問者]** コンテナをネストします。
* このレポートはセグメンテーションをサポートしていません。
* セグメント化条件に一致するデータはありません。

## セグメントマネージャーで作成したセグメントが表示されないのはなぜですか？ {#invisible}

考えられる理由：

* 一部のディメンションは、Data Warehouseでのみ使用でき、セグメントマネージャーでは使用できません。
* セグメントは、特定のレポートスイートに対してのみチェックされます。
* 共有セグメントは、別のユーザーによって削除された可能性があります。
* データセンターまたはブラウザーのキャッシュの問題により、セグメントを読み込めませんでした。
* セグメントは保存されていません。
* IP アドレスはユーザー側でブロックされる場合があります。

## セグメントを適用した後に表示されるデータが正しくないように見えるのはなぜですか？ {#page-data}

考えられる理由：

* ルールまたは演算子が、必要な結果に対して正しくありません。
* セグメント内のコンテナの誤った使用。
* セグメントに使用されるトラフィック変数が正しく設定されていないか、有効期限が切れています。
