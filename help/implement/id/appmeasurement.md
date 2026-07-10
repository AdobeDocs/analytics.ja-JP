---
title: AppMeasurementを使用した訪問者の特定
description: AppMeasurementを使用してAdobe Analyticsを実装する際に、訪問者を正しく識別する。
exl-id: 38797ca5-dc53-431e-95df-3c9e68aead94
TQID: https://experienceleague.adobe.com/vWLzF0HXreytCKr01H4-gKzNlO36ySHA2vbcHvT3cIw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 519
ht-degree: 1%

---

# AppMeasurementを使用した訪問者の特定

AppMeasurementは、Adobe Analyticsのデータ収集用の従来のJavaScriptライブラリです。 AppMeasurement自体は、訪問者を識別するネイティブな方法を提供しますが、多くのモダンなブラウザーは、設定しようとするサードパーティ Cookieを拒否します。 Adobeでは、最新のブラウザーのプライバシー標準に準拠するために、すべての実装で[Adobe Visitor ID サービス ](https://experienceleague.adobe.com/ja/docs/id-service/using/home)を使用することを強くお勧めします。 AppMeasurementのすべてのバージョンには、訪問者ID サービスの実装に使用されるJavaScript ライブラリ `VisitorAPI.js`がバンドルされています。

## 訪問者ID サービスを使用した訪問者の識別（推奨）

次の手順に従って準備を進めてください。

* [最新バージョンのAppMeasurement](https://github.com/adobe/appmeasurement)をダウンロードします。 ダウンロードされたライブラリには、`AppMeasurement.js`と`VisitorAPI.js`の両方が含まれています。
* 開発[ レポートスイート ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)。
* [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md)の目的のエッジ ドメイン。
* IMS組織ID:
   1. Adobe IDの資格情報を使用して[Adobe CX Enterprise](https://experience.adobe.com)にログインします。
   1. CX Enterprise インターフェイスの任意の場所で、`[Cmd]` + `[I]` （iOS）または`[Ctrl]` + `[I]` （Windows）を押します。
   1. **[!UICONTROL ユーザーデータデバッガー]**&#x200B;が表示されます。 「**[!UICONTROL 割り当てられた組織]**」タブを選択します。
   1. 目的のIMS組織を展開します。
   1. **[!UICONTROL ID]** フィールドを探します。

上記のリソースが揃えば、次の基本的な例ページには、Adobe Analyticsにデータを送信するために必要な最小限の呼び出しが含まれています。

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
>ヒットが訪問者ID サービスを使用しているかどうかを追跡するには、`Visitor`の存在を[`doPlugins`](/help/implement/vars/functions/doplugins.md)のカスタム変数に割り当てます。
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## `s_vi` Cookieを使用した訪問者の識別（非推奨）

>[!IMPORTANT]
>
>Adobeでは、この方法を使用して訪問者を識別しないようにお勧めします。

組織が訪問者ID サービス （`VisitorAPI.js`）を使用しない場合、AppMeasurementは独自の従来の形式の訪問者識別を使用します。 訪問者が初めてサイトにアクセスすると、ライブラリは[`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookieをチェックします。 このCookieは、[`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) （HTTPSの場合）または`trackingServer` （HTTPの場合）に一致するドメインに設定されます。

* [管理証明書プログラム ](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert)に参加している場合、トラッキングサーバーは通常1st パーティドメインとなり、`s_vi`個のCookieが1st パーティになります。
* 管理証明書プログラムに参加しない場合、トラッキングサーバーは通常、`adobedc.net`、`omtrdc.net`または`2o7.net`のサブドメインであり、`s_vi` Cookieはサードパーティ Cookieになります。 最新のブラウザープライバシー基準により、サードパーティ Cookieは、ほとんどのブラウザーで拒否されます。 拒否されると、AppMeasurementは代わりにファーストパーティのフォールバッククッキー（`fid`）を設定しようとします。

`trackingServerSecure`を正しく設定した場合、追加の訪問者識別手段は必要ありません。

## `visitorID`を使用した訪問者の識別（非推奨）

>[!IMPORTANT]
>
>Adobeでは、この方法を使用して訪問者を識別しないようにお勧めします。

[`visitorID`](/help/implement/vars/config-vars/visitorid.md)変数を使用すると、組織は訪問者を特定するための完全な独立した制御を実行できます。 `visitorID`を使用する場合は、次の制限事項に注意してください。

* すべてのヒットには、1人の訪問者としてカウントするために同じ`visitorID`値が含まれている必要があります。
   * `visitorID`を省略したヒットは、別の訪問者識別方法を自動的に使用し、別の訪問者として扱います。
   * 以前のヒットとは異なる`visitorID`値を含むヒットは、別の訪問者として扱われます。
   * Adobeでは、Adobe Analyticsで異なる訪問者IDを使用してヒットを合成する方法は提供されていません。
* 共有オーディエンス、Analytics for Targetおよび顧客属性は、`visitorID`を使用して識別された訪問者ではサポートされていません。

この変数を使用した実装手順については、[`visitorID`](/help/implement/vars/config-vars/visitorid.md)を参照してください。
