---
title: AppMeasurementを使用した訪問者の識別
description: AppMeasurementを使用してAdobe Analyticsを実装する場合に、訪問者を正しく識別する。
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# AppMeasurementを使用した訪問者の識別

AppMeasurementは、Adobe Analyticsの従来のデータ収集用JavaScript ライブラリです。 AppMeasurement自体は訪問者を識別するネイティブな手段を提供しますが、多くの最新のブラウザーは、設定しようとするサードパーティ cookie を拒否します。 Adobeでは、最新のブラウザープライバシー標準に準拠するために、すべての実装でAdobe Experience Cloud訪問者 ID サービスを使用することを強くお勧めします。 AppMeasurementのすべてのバージョンには、訪問者 ID サービスの実装に使用されるJavaScript ライブラリである `VisitorAPI.js` がバンドルされています。

## 訪問者 ID サービスを使用した訪問者の識別（推奨）

次の準備が整っていることを確認します。

* [AppMeasurementの最新バージョン &#x200B;](https://github.com/adobe/appmeasurement) をダウンロードします。 ダウンロードしたライブラリには、`AppMeasurement.js` と `VisitorAPI.js` の両方が含まれています。
* 開発 [&#x200B; レポートスイート ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)。
* [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) の目的のエッジドメイン。
* IMS 組織 ID :
   1. Adobe IDの資格情報を使用して [experience.adobe.com](https://experience.adobe.com) にログインします。
   1. Experience Cloud インターフェイスの任意の場所で、`[Cmd]` + `[I]` （iOS）または `[Ctrl]` + `[I]` （Windows）を押します。
   1. **[!UICONTROL ユーザーデータデバッガー]** が表示されます。 「**[!UICONTROL 割り当てられた組織]**」タブを選択します。
   1. 目的の IMS 組織を展開します。
   1. 「**[!UICONTROL ID]**」フィールドを見つけます。

上記のリソースを取得したら、次の基本的なサンプルページに、Adobe Analyticsにデータを送信するために必要な最小限の呼び出しが含まれます。

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>ヒットが訪問者 ID サービスを使用しているかどうかを追跡するには、`Visitor` のカスタム変数に [`doPlugins`](/help/implement/vars/functions/doplugins.md) の存在を割り当てます。
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## `s_vi` cookie を使用した訪問者の識別（推奨しません）

>[!IMPORTANT]
>
>Adobeでは、この手法を使用して訪問者を特定することはお勧めしません。

組織で訪問者 ID サービスを使用しない場合、AppMeasurementは独自の訪問者識別形式を使用します。 訪問者が初めてサイトに到達すると、ライブラリは [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie をチェックします。 この cookie は、[`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) （HTTPS の場合）または [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) （HTTP の場合）に一致するドメインに設定されます。

* [Managed certificate program](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert) に参加する場合、トラッキングサーバーは通常、ファーストパーティドメインで、Cookie がファーストパーティ `s_vi` なっています。
* 管理証明書プログラムに参加していない場合、トラッキングサーバーは通常、`adobedc.net`、`omtrdc.net`、`2o7.net` のサブドメインであり、`s_vi` cookie をサードパーティ cookie にします。 最新のブラウザープライバシー標準により、ほとんどのブラウザーでサードパーティ cookie が拒否されます。 拒否されると、AppMeasurementは代わりにファーストパーティ フォールバック cookie （`fid`）を設定しようとします。

`trackingServerSecure` を正しく設定した場合、それ以上の訪問者識別測定は必要ありません。

## `visitorID` を使用して訪問者を識別する（推奨しません）

>[!IMPORTANT]
>
>Adobeでは、この手法を使用して訪問者を特定することはお勧めしません。

[`visitorID`](/help/implement/vars/config-vars/visitorid.md) 変数を使用すると、組織が訪問者を完全に独立して識別できます。 `visitorID` を使用する場合は、次の制限事項に注意してください。

* 単一の訪問者としてカウントされるには、すべてのヒットに同じ `visitorID` 値が含まれている必要があります。
   * `visitorID` を省略したヒットは、自動的に別の訪問者識別方法を使用して、別の訪問者として扱います。
   * 以前のヒットと異なる `visitorID` 値を含むヒットは、別の訪問者として扱われます。
   * Adobeでは、異なる訪問者 ID を使用してヒットをステッチする方法は提供されていません。
* 共有オーディエンス、Analytics for Target および顧客属性は、`visitorID` を使用して識別された訪問者ではサポートされません。

この変数を使用した実装手順については、[`visitorID`](/help/implement/vars/config-vars/visitorid.md) を参照してください。
