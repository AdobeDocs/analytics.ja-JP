---
title: Adobe Analytics タグ拡張機能を使用した訪問者特定
description: Adobe Analytics タグ拡張機能を実装する際に、訪問者を正しく識別する。
exl-id: de534c69-0f43-45eb-86da-20d3cd3f363d
TQID: https://experienceleague.adobe.com/bdm2phkscnH9bSiQqK9K--ySTLguGaf-WLgEc3TL6H8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 499
ht-degree: 2%

---

# Adobe Analytics タグ拡張機能を使用した訪問者特定

Adobe Analytics タグ拡張機能を使用すると、タグ管理インターフェイスを使用してAppMeasurementを実装できます。 このタグ拡張機能は、基本的に内部にAppMeasurementが含まれているため、訪問者を識別するための同様の方法を提供し、訪問者ID サービス用に別のタグ拡張機能が必要です。

## 訪問者ID サービスを使用した訪問者の識別（推奨）

Adobe Analytics タグ拡張機能を使用して訪問者ID サービスを使用するには、タグプロパティにExperience Cloud ID サービスタグ拡張機能を含めます。

1. Adobe IDの資格情報を使用して[Adobe CX Enterprise](https://experience.adobe.com)にログインします。
1. **[!UICONTROL データ収集]** > **[!UICONTROL タグ]**&#x200B;に移動します。
1. 目的のタグプロパティを見つけます。
1. **[!UICONTROL 拡張機能]**&#x200B;に移動し、「**[!UICONTROL カタログ]**」タブを選択します。
1. **[!UICONTROL Experience Cloud ID サービス]**&#x200B;拡張機能を探し、**[!UICONTROL インストール]**&#x200B;を選択します。

タグ拡張機能はIMS組織IDを自動的に取得するため、追加の設定は必要ありません。

## `s_vi` Cookieを使用した訪問者の識別（非推奨）

>[!IMPORTANT]
>
>Adobeでは、この方法を使用して訪問者を識別しないようにお勧めします。

Visitor ID Service タグ拡張機能を使用しない場合、Adobe Analytics タグ拡張機能は独自の形式の訪問者識別を使用します。 訪問者が初めてサイトにアクセスすると、拡張機能は[`s_vi`](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/cookies/analytics) Cookieをチェックします。 このCookieは、[&#x200B; タグ拡張機能の設定時](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/analytics/overview)に&#x200B;**[!UICONTROL SSL トラッキングサーバー]** （HTTPSの場合）または&#x200B;**[!UICONTROL トラッキングサーバー]** （HTTPの場合）に一致するドメインに設定されます。

* [管理証明書プログラム &#x200B;](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/adobe-managed-cert)に参加している場合、トラッキングサーバーは通常1st パーティドメインとなり、`s_vi`個のCookieが1st パーティになります。
* 管理証明書プログラムに参加しない場合、トラッキングサーバーは通常、`adobedc.net`、`omtrdc.net`または`2o7.net`のサブドメインであり、`s_vi` Cookieはサードパーティ Cookieになります。 最新のブラウザープライバシー基準により、サードパーティ Cookieは、ほとんどのブラウザーで拒否されます。 拒否されると、AppMeasurementは代わりにファーストパーティのフォールバッククッキー（`fid`）を設定しようとします。

[!UICONTROL SSL トラッキングサーバー]を正しく設定した場合、追加の訪問者識別手段は必要ありません。

## `visitorID`を使用した訪問者の識別（非推奨）

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
