---
title: トラッキングオプトアウト理由
description: プライバシー設定を有効にした場合に除外されるデータをプレビューします。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 11%

---

# トラッキングオプトアウト理由

*このページは、特定のレポートスイート設定を有効にすることで、潜在的なデータへの影響を確認できる[&#x200B; ディメンション &#x200B;](overview.md)を指します。 [Adobe Experience Cloud ID オプトインサービス &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)とは関係ありません。*

「トラッキングのオプトアウト理由」ディメンションは、プライバシー設定を有効にした場合に除外されるデータのプレビューとして機能します。 このディメンションは、主に、レポートスイート設定で[&#x200B; プライバシー設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=ja)を有効にした場合に、実装が悪影響を受けるかどうかを判断するために使用されます。

プライバシー設定がまだ有効になっていない場合、一般的な実装では、このディメンションの下にレポートスイート全体のトラフィックの1%以下が表示されます。 全トラフィックの1%を超える割合では、AppMeasurementがファーストパーティ Cookieを設定できない潜在的な実装上の問題が考えられます。

## このディメンションへのデータ入力

このディメンションは、[&#x200B; プライバシー設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=ja)をまだ有効にしていないすべての実装に対して、標準搭載で機能します。 デスクトップとモバイルの両方のブラウザーのすべてのCookie **設定をブロックした** ユーザーの削除が既に有効になっている場合、このディメンションにはデータは含まれません。

## ディメンション項目

ディメンション項目には、`"Cookies disabled by Desktop Browser"` および `"Cookies disabled by Mobile Browser"` が含まれます。

* **デスクトップブラウザーによって無効になったCookie**：訪問者はデスクトップブラウザーを使用してCookieをブロックし、**[!UICONTROL デスクトップブラウザーですべてのCookieをブロックしたユーザーを削除]**&#x200B;は無効になっています。
* **モバイルブラウザーによって無効なCookie**：訪問者はモバイルブラウザーを使用してCookieをブロックしました。**[!UICONTROL モバイルブラウザーですべてのCookieをブロックしたユーザーを削除]**&#x200B;は無効です。
