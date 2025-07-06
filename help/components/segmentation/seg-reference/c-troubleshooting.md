---
description: セグメントに関連する問題のトラブルシューティングおよび修正方法を説明します。
title: トラブルシューティング
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 42%

---

# トラブルシューティング

この記事では、セグメントに関するよくある問題と、そのトラブルシューティング方法について説明します。

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## セグメントからデータがまったく返されないのはなぜですか。 {#no-data}

考えられる理由は次のとおりです。

* 逆ネスト – 例えば、![User](/help/assets/icons/User.svg)**[!UICONTROL Visitor]** コンテナを ![Visit](/help/assets/icons/Visit.svg)**[!UICONTROL Visit]** コンテナの下にネストします。
* レポートがセグメントをサポートしていない。
* セグメント基準に一致するデータがない。

## 作成したセグメントがセグメントマネージャーに表示されないのはなぜですか？ {#invisible}

考えられる理由は次のとおりです。

* 一部のディメンションはData Warehouseでのみ使用でき、セグメントマネージャーでは使用できません。
* セグメントが特定のレポートスイートに対してのみチェックされている。
* 共有セグメントが別のユーザーによって削除されている。
* データセンターまたはブラウザーのキャッシュの問題が原因で、セグメントを読み込めませんでした。
* セグメントが保存されていない。
* IP アドレスがユーザー側でブロックされている。

## セグメントを適用した後に表示されるデータが間違っているように見えるのはなぜですか？ {#page-data}

考えられる理由は次のとおりです。

* ルールまたは演算子が、必要な結果に対して正しくありません。
* セグメントでのコンテナの誤った使用。
* セグメントに使用するトラフィック変数が適切に設定されていないか、期限切れになっている。
