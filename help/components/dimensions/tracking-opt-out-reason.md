---
title: トラッキングオプトアウト理由
description: プライバシー設定を有効にした場合に除外されるデータをプレビューします。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 7%

---

# トラッキングオプトアウト理由

*このページでは、特定のレポートスイート設定を有効にした場合にデータに与える可能性のある影響を確認できる [ ディメンション ](overview.md) について説明します。 [Adobe Experience Cloud ID オプトインサービス ](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja) とは関係ありません*

「トラッキングオプトアウト理由」ディメンションは、プライバシー設定を有効にした場合に除外されるデータへのプレビューとして機能します。 このディメンションは、主に、レポートスイート設定で [ プライバシー設定 ](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) を有効にした場合に、実装が悪影響を受けるかどうかを判断するために使用されます。

プライバシー設定がまだ有効になっていない場合、一般的な実装では、このディメンションでレポートスイート全体のトラフィックの 1% 以下が表示されます。 すべてのトラフィックの 1% を超える割合は、実装に問題があり、AppMeasurementでファーストパーティ cookie を設定できない可能性を示しています。

## このディメンションへのデータ入力

このディメンションは、まだ有効にしていない [ プライバシー設定 ](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) すべての実装に対して初期設定の状態で動作します。 組織がデスクトップブラウザーとモバイルブラウザーの両方で既に **[!UICONTROL すべての Cookie をブロックしたユーザーを削除]** 設定を有効にしている場合、このディメンションにはデータが含まれていません。

## ディメンション項目

ディメンション項目には、`"Cookies disabled by Desktop Browser"` および `"Cookies disabled by Mobile Browser"` が含まれます。

* **デスクトップブラウザーによって無効にされた Cookie**：訪問者がデスクトップブラウザーを使用して Cookie をブロックし、**[!UICONTROL デスクトップブラウザーですべての Cookie をブロックしたユーザーを削除]** が無効になっています。
* **モバイルブラウザーによって無効にされた Cookie**：訪問者がモバイルブラウザーを使用して Cookie をブロックし、**[!UICONTROL モバイルブラウザーですべての Cookie をブロックしたユーザーを削除]** が無効になっています。
