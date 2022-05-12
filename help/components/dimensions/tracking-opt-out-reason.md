---
title: トラッキングオプトアウト理由
description: プライバシー設定を有効にした場合に除外されるデータのプレビュー
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: 4c896fe930b52e440f8b91725fa6451faaa76fc8
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 7%

---

# トラッキングオプトアウト理由

「トラッキングのオプトアウト理由」ディメンションは、プライバシー設定を有効にした場合に除外されるデータのプレビューとして機能します。 このディメンションは主に、を有効にした場合に実装が悪影響を受けるかどうかを判断するために使用されます [プライバシー設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) 」をクリックします。

プライバシー設定がまだ有効になっていない場合、一般的な実装では、このディメンションでのレポートスイートの全体的なトラフィックの 1%以下が表示されます。 すべてのトラフィックの 1%を超える割合が高い場合、AppMeasurement がファーストパーティ Cookie を設定できない実装上の問題が発生する可能性があります。

## このディメンションへのデータ入力

このディメンションは、まだ有効になっていないすべての実装で初期設定の状態で機能します [プライバシー設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). 組織が既に **[!UICONTROL すべての Cookie をブロックしたユーザーを削除]** デスクトップブラウザーとモバイルブラウザーの両方で、このディメンションにはデータが含まれていません。

## ディメンション項目

ディメンション項目には、`"Cookies disabled by Desktop Browser"` および `"Cookies disabled by Mobile Browser"` が含まれます。

* **デスクトップブラウザーで無効にされた cookie**:訪問者がデスクトップブラウザーで cookie をブロックし、 **[!UICONTROL デスクトップブラウザーですべての Cookie をブロックしたユーザーを除外]** は無効です。
* **モバイルブラウザーによって無効にされた cookie**:訪問者がモバイルブラウザーで cookie をブロックし、 **[!UICONTROL モバイルブラウザーですべての Cookie をブロックしたユーザーを除外]** は無効です。
