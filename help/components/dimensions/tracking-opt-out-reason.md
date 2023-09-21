---
title: トラッキングオプトアウト理由
description: プライバシー設定を有効にした場合に除外されるデータのプレビュー。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# トラッキングオプトアウト理由

*このページでは、 [ディメンション](overview.md) を使用すると、特定のレポートスイート設定を有効にした場合にデータに与える影響を確認できます。 これは、 [Adobe Experience Cloud ID オプトインサービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja).*

「トラッキングのオプトアウト理由」ディメンションは、プライバシー設定を有効にした場合に除外されるデータのプレビューとして機能します。 このディメンションは主に、を有効にした場合に実装が悪影響を受けるかどうかを判断するために使用されます [プライバシー設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) 」をクリックします。

プライバシー設定がまだ有効になっていない場合、一般的な実装では、このディメンションでのレポートスイートの全体的なトラフィックの 1%以下が表示されます。 すべてのトラフィックの 1%を超える割合がAppMeasurementのファーストパーティ cookie 設定を妨げる実装上の問題が生じる可能性があることを示しています。

## このディメンションへのデータ入力

このディメンションは、まだ有効になっていないすべての実装で初期設定の状態で機能します [プライバシー設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). 組織が既に **[!UICONTROL すべての Cookie をブロックしたユーザーを削除する]** デスクトップブラウザーとモバイルブラウザーの両方で、このディメンションにはデータが含まれていません。

## ディメンション項目

ディメンション項目には、`"Cookies disabled by Desktop Browser"` および `"Cookies disabled by Mobile Browser"` が含まれます。

* **デスクトップブラウザーで無効にされた cookie**：訪問者がデスクトップブラウザーで cookie をブロックしており、 **[!UICONTROL デスクトップブラウザーですべての Cookie をブロックしたユーザーを除外]** は無効です。
* **モバイルブラウザーによって無効にされた cookie**：訪問者がモバイルブラウザーで cookie をブロックしており、 **[!UICONTROL モバイルブラウザーですべての Cookie をブロックしたユーザーを除外]** は無効です。
