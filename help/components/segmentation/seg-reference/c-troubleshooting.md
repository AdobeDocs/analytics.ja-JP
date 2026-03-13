---
description: セグメントに関連する問題のトラブルシューティングおよび修正方法を説明します。
title: トラブルシューティング
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 50e6a09e62db60a765da05fa65089a006f103a2b
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%

---

# トラブルシューティング

この記事では、セグメントに関するよくある問題と、そのトラブルシューティング方法について説明します。

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## セグメントがデータをまったく返さないのはなぜですか？ {#no-data}

考えられる理由：

* 逆ネスト – 例えば、![User](/help/assets/icons/User.svg)**[!UICONTROL Visitor]** コンテナを ![Visit](/help/assets/icons/Visit.svg)**[!UICONTROL Visit]** コンテナの下にネストします。
* レポートはセグメント化をサポートしていません。
* セグメント化条件に一致するデータがありません。

## 作成したセグメントがセグメントマネージャーに表示されないのはなぜですか？ {#invisible}

考えられる理由：

* 一部のディメンションはData Warehouseでのみ使用でき、セグメントマネージャーでは使用できません。
* 特定のレポートスイートに対してのみセグメントがオンになります。
* 共有セグメントが別のユーザーによって削除された可能性があります。
* データセンターまたはブラウザーのキャッシュの問題が原因で、セグメントを読み込めませんでした。
* セグメントが保存されていません。
* IP アドレスは、ユーザー側でブロックされる場合があります。

## セグメントを適用した後に表示されるデータが間違っているように見えるのはなぜですか？ {#page-data}

考えられる理由：

* ルールまたは演算子が、必要な結果に対して正しくありません。
* セグメントでのコンテナの誤った使用。
* セグメント化に使用するトラフィック変数が正しく設定されていないか、有効期限が切れています。
