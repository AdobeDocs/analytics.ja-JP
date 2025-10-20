---
title: Adobe Analytics タグ拡張機能を使用した訪問者の識別
description: Adobe Analytics タグ拡張機能を実装する際に、訪問者を正しく識別します。
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Adobe Analytics タグ拡張機能を使用した訪問者の識別

Adobe Analytics タグ拡張機能を使用すると、タグ管理インターフェイスを使用してAppMeasurementを実装できます。 このタグ拡張は基本的に内部のAppMeasurementなので、訪問者を識別するための同様の方法を提供し、訪問者 ID サービス用に別のタグ拡張を必要とします。

## 訪問者 ID サービスを使用した訪問者の識別（推奨）

Adobe Analytics タグ拡張機能で訪問者 ID サービスを使用するには、タグプロパティにExperience Cloud ID サービスタグ拡張機能を含めます。

1. Adobe IDの資格情報を使用して [experience.adobe.com](https://experience.adobe.com) にログインします。
1. **[!UICONTROL データ収集]**/**[!UICONTROL タグ]** に移動します。
1. 目的のタグプロパティを見つけます。
1. **[!UICONTROL 拡張機能]** に移動し、「**[!UICONTROL カタログ]**」タブを選択します。
1. **[!UICONTROL Experience Cloud ID サービス]** 拡張機能を見つけ、「**[!UICONTROL インストール]**」を選択します。

タグ拡張機能は IMS 組織 ID を自動的に取得するので、追加の設定は必要ありません。

## `s_vi` cookie を使用した訪問者の識別（推奨しません）

>[!IMPORTANT]
>
>Adobeでは、この手法を使用して訪問者を特定することはお勧めしません。

訪問者 ID サービスタグ拡張機能を使用しない場合、Adobe Analytics タグ拡張機能は独自の訪問者識別形式を使用します。 訪問者が初めてサイトに到達すると、拡張機能は [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie を確認します。 この cookie は、**[!UICONTROL タグ拡張機能の設定]** 時に、**[!UICONTROL SSL トラッキングサーバー]** （HTTPS の場合）または [&#x200B; トラッキングサーバー &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) （HTTP の場合）に一致するドメインに設定されます。

* [Managed certificate program](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert) に参加する場合、トラッキングサーバーは通常、ファーストパーティドメインで、Cookie がファーストパーティ `s_vi` なっています。
* 管理される証明書プログラムに参加していない場合、トラッキングサーバーは通常、`adobedc.net`、`omtrdc.net` または `2o7.net` のサブドメインであり、`s_vi` cookie をサードパーティ cookie にします。 最新のブラウザープライバシー標準により、ほとんどのブラウザーでサードパーティ cookie が拒否されます。 拒否されると、AppMeasurementは代わりにファーストパーティ フォールバック cookie （`fid`）を設定しようとします。

[!UICONTROL SSL トラッキングサーバー &#x200B;] を正しく設定した場合、それ以上の訪問者識別測定は必要ありません。

## `visitorID` を使用して訪問者を識別する（推奨しません）

>[!IMPORTANT]
>
>Adobeでは、この手法を使用して訪問者を特定することはお勧めしません。

**[!UICONTROL 訪問者 ID]** 変数を使用すると、組織は訪問者を完全に独立して識別できます。 データ要素を使用して [!UICONTROL &#x200B; 訪問者 ID] を設定する場合は、次の制限事項に注意してください。

* 各ヒットが単一の訪問者としてカウントされるには、同じ [!UICONTROL &#x200B; 訪問者 ID] 値を含む必要があります。
   * [!UICONTROL &#x200B; 訪問者 ID] データ要素を省略するヒットでは、自動的に別の訪問者識別方法を使用して、別の訪問者として扱います。
   * 以前のヒットと異なる [!UICONTROL &#x200B; 訪問者 ID] 値を含むヒットは、別の訪問者として扱われます。
   * Adobeでは、異なる訪問者 ID を使用してヒットをステッチする方法は提供されていません。
* 共有オーディエンス、Analytics for Target および顧客属性は、[!UICONTROL &#x200B; 訪問者 ID] を使用して識別された訪問者ではサポートされません。

この変数を使用した実装手順については、[`visitorID`](/help/implement/vars/config-vars/visitorid.md) を参照してください。
