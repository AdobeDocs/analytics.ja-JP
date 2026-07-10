---
title: Adobe Analytics タグ拡張機能を使用した訪問者特定
description: Adobe Analytics タグ拡張機能を実装する際に、訪問者を正しく識別する。
exl-id: de534c69-0f43-45eb-86da-20d3cd3f363d
TQID: 'https://experienceleague.adobe.com/i38Vo-39aUwJOp3HoS-bb2jqwSSV0oqeR0lkjOJqcgs'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e4f5f438-eabb-4c54-9133-b817e3d125f5
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 505
ht-degree: 2%

---

# Adobe Analytics タグ拡張機能を使用した訪問者特定

Adobe Analytics タグ拡張機能を使用すると、タグ管理インターフェイスを使用してAppMeasurementを実装できます。 このタグ拡張機能は、基本的に内部にAppMeasurementを実装しているため、訪問者を識別する同様の方法を提供し、ECIDを収集するには別のタグ拡張機能が必要です。

## 訪問者ID サービスを使用した訪問者の識別（推奨）

Adobe Analytics タグ拡張機能を使用して訪問者ID サービスを使用するには、タグプロパティに[!UICONTROL Experience Cloud ID サービス ] タグ拡張機能（訪問者ID サービスを実装）を含めます。

1. Adobe IDの資格情報を使用して[Adobe CX Enterprise](https://experience.adobe.com)にログインします。
1. **[!UICONTROL データ収集]** > **[!UICONTROL タグ]**&#x200B;に移動します。
1. 目的のタグプロパティを見つけます。
1. **[!UICONTROL 拡張機能]**&#x200B;に移動し、「**[!UICONTROL カタログ]**」タブを選択します。
1. **[!UICONTROL Experience Cloud ID サービス]**&#x200B;拡張機能を見つけ、**[!UICONTROL インストール]**&#x200B;を選択します。

タグ拡張機能はIMS組織IDを自動的に取得するため、追加の設定は必要ありません。

## `s_vi` Cookieを使用した訪問者の識別（推奨されません）

>[!IMPORTANT]
>
>Adobeでは、この方法を使用して訪問者を識別しないようにお勧めします。

お客様の組織が[!UICONTROL Experience Cloud ID Service] タグ拡張機能を使用しない場合、Adobe Analytics タグ拡張機能は独自の従来の形式の訪問者識別を使用します。 訪問者が初めてサイトにアクセスすると、拡張機能は[`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookieをチェックします。 このCookieは、[ タグ拡張機能の設定時](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/analytics/overview)に&#x200B;**[!UICONTROL SSL トラッキングサーバー]** （HTTPSの場合）または&#x200B;**[!UICONTROL トラッキングサーバー]** （HTTPの場合）に一致するドメインに設定されます。

* [管理証明書プログラム ](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert)に参加している場合、トラッキングサーバーは通常1st パーティドメインとなり、`s_vi`個のCookieが1st パーティになります。
* 管理証明書プログラムに参加しない場合、トラッキングサーバーは通常、`adobedc.net`、`omtrdc.net`または`2o7.net`のサブドメインであり、`s_vi` Cookieはサードパーティ Cookieになります。 最新のブラウザープライバシー基準により、サードパーティ Cookieは、ほとんどのブラウザーで拒否されます。 拒否されると、AppMeasurementは代わりにファーストパーティのフォールバッククッキー（`fid`）を設定しようとします。

[!UICONTROL SSL トラッキングサーバー]を正しく設定した場合、追加の訪問者識別手段は必要ありません。

## `visitorID`を使用した訪問者の識別（推奨されません）

>[!IMPORTANT]
>
>Adobeでは、この方法を使用して訪問者を識別しないようにお勧めします。

**[!UICONTROL 訪問者ID]**&#x200B;変数を使用すると、組織は訪問者を特定するための完全な独立した制御を実行できます。 データ要素を使用して[!UICONTROL 訪問者ID]を設定する場合は、次の制限事項に注意してください。

* すべてのヒットには、単一の訪問者としてカウントするために、同じ[!UICONTROL 訪問者ID]値が含まれている必要があります。
   * [!UICONTROL 訪問者ID] データ要素を省略したヒットは、別の訪問者識別方法を自動的に使用し、別の訪問者として扱います。
   * 以前のヒットとは異なる[!UICONTROL 訪問者ID]値を含むヒットは、別の訪問者として扱われます。
   * Adobeでは、Adobe Analyticsで異なる訪問者IDを使用してヒットを合成する方法は提供されていません。
* [!UICONTROL 訪問者ID]を使用して識別された訪問者では、共有オーディエンス、Target用Analyticsおよび顧客属性はサポートされていません。

この変数を使用した実装手順については、[`visitorID`](/help/implement/vars/config-vars/visitorid.md)を参照してください。
