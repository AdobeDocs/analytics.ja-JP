---
title: AppMeasurementから Web SDK への移行
description: AppMeasurement JavaScript ライブラリから Web SDK JavaScript ライブラリにAdobe Analytics実装を更新します。
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 0%

---

# AppMeasurementから Web SDK への移行

この実装パスには、AppMeasurement実装から Web SDK JavaScript ライブラリ実装に移行するための系統的な移行アプローチが含まれます。 その他の実装パスについては、次の別のページで説明しています。

* [Analytics 拡張機能から Web SDK 拡張機能へ](analytics-extension-to-web-sdk.md):Adobe Analytics タグ拡張機能から Web SDK タグ拡張機能に移行するためのスムーズで系統的なアプローチを採用します。 このアプローチにより、Customer Journey AnalyticsなどのAdobe Experience Platform サービスを使用する準備が整うまで XDM を使用する必要がなくなります。 の使用 `data` の代わりにのオブジェクト `xdm` Adobeにデータを送信するオブジェクト。
* [Web SDK JavaScript ライブラリ](web-sdk-javascript-library.md):Web SDK JavaScript ライブラリを使用した新規 Web SDK インストール（`alloy.js`）に設定します。 タグ UI を使用する代わりに、自分で実装を管理します。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。
* [Web SDK タグ拡張機能](web-sdk-tag-extension.md):Adobe Experience Platform Data Collection のタグを使用して実装を管理する、新しい Web SDK インストール。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。

## この実装パスのメリットとデメリット

この移行アプローチを使用すると、メリットとデメリットの両方が生じます。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**既存の実装を使用**：このアプローチでは、いくつかの実装変更が必要ですが、ゼロから完全に新しい実装を行う必要はありません。 実装ロジックへの最小限の変更で、既存のデータレイヤーとコードを使用できます。</li><li>**スキーマは必要ありません**:Web SDK への移行のこの段階では、XDM スキーマは必要ありません。 代わりに、にデータを入力できます `data` オブジェクト。Adobe Analyticsにデータを直接送信します。 Web SDK への移行が完了したら、組織のスキーマを作成し、データストリームマッピングを使用して適用可能な XDM フィールドを入力できます。 移行プロセスのこの段階でスキーマが必要だった場合、組織はAdobe Analytics XDM スキーマの使用を強制されます。 このスキーマを使用すると、組織が今後独自のスキーマを使用するのが難しくなります。</li></ul> | <ul><li>**実装を変更するには、開発者の介入が必要です**:Web SDK 実装を変更する場合は、開発チームと協力してサイトのコードを編集する必要があります。 というアプローチ [web SDK タグ拡張機能に移行します](analytics-extension-to-web-sdk.md) この欠点を回避します。</li><li>**技術的債務の履行**：このアプローチは既存の実装の変更済み形式を使用するので、実装ロジックを追跡し、必要に応じて将来変更を実行するのが難しい場合があります。</li><li>**Platform にデータを送信するには、マッピングが必要です**:Customer Journey Analyticsを使用する準備が整ったら、Adobe Experience Platformのデータセットにデータを送信する必要があります。 このアクションでは、のすべてのフィールドが `data` オブジェクトは、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリです。 マッピングは、このワークフローに対して 1 回だけ行う必要があります。実装の変更は必要ありません。 ただし、XDM オブジェクトでデータを送信する場合に必要ない追加の手順です。</li></ul> |

Adobeでは、次のシナリオでこの実装パスを使用することをお勧めします。

* 既存の実装がある場合は、Adobe Analytics AppMeasurement JavaScript ライブラリを使用します。 Adobe Analytics タグ拡張機能を使用した実装がある場合は、次の手順に従います [Adobe Analyticsのタグ拡張機能から Web SDK のタグ拡張機能への移行](analytics-extension-to-web-sdk.md) その代わり。
* 今後Customer Journey Analyticsを使用するが、Analytics 実装を Web SDK 実装に最初から置き換える必要がない。 Web SDK で実装をゼロから置き換えることは最も努力が必要ですが、最も実行可能な長期的な実装アーキテクチャも提供します。 組織がクリーンな Web SDK 実装の作業を進んで行う場合は、を参照してください。 [Adobe Experience Platform Web SDK を使用したデータの取り込み](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) （Customer Journey Analyticsユーザーガイド）を参照してください。

## Web SDK への移行に必要な手順

以下の手順には、取り組むべき具体的な目標が含まれています。 各手順をクリックすると、実行方法に関する詳細な手順が表示されます。

+++**1.データストリームの作成と設定**

Adobe Experience Platform Data Collection にデータストリームを作成します。 このデータストリームにデータを送信すると、データがAdobe Analyticsに転送されます。 今後、この同じデータストリームがCustomer Journey Analyticsにデータを転送します。

1. に移動します。 [experience.adobe.com](https://experience.adobe.com) 認証情報を使用してログインします。
1. 右上のホームページまたは製品セレクターを使用して、に移動します **[!UICONTROL データ収集]**.
1. 左側のナビゲーションで、を選択します。 **[!UICONTROL データストリーム]**.
1. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。
1. 目的の名前を入力し、を選択します **[!UICONTROL 保存]**.
1. データストリームを作成したら、次を選択します。 **[!UICONTROL サービスを追加]**.
1. サービスのドロップダウンメニューで、を選択します **[!UICONTROL Adobe Analytics]**.
1. 分析データを現在送信しているサイトと同じレポートスイート ID を入力します。 「**[!UICONTROL 保存]**」をクリックします。

![Adobe Analytics サービスを追加](assets/datastream-rsid.png) {style="border:1px solid gray"}

これで、データストリームがデータを受け取り、Adobe Analyticsに渡す準備が整いました。 データストリーム ID をメモします。この ID は、コードで Web SDK を設定する際に必要になるからです。

+++

+++**2. Web SDK JavaScript ライブラリのインストール**

の最新バージョンを参照します `alloy.js` そのため、そのメソッド呼び出しを使用できます。 参照： [JavaScript ライブラリを使用した Web SDK のインストール](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) を参照してください（詳細および使用するコードブロック）。

+++

+++**3.Web SDK の設定**

Web SDK を使用して、前の手順で作成したデータストリームを指すように実装を設定します [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) コマンド。 この `configure` コマンドは、ライブラリのインストールコードと一緒に含めることができるように、すべてのページで設定する必要があります。

の使用 [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) および [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) web SDK 内のプロパティ `configure` コマンド：

* を `edgeConfigId` を前の手順で取得したデータストリーム ID に変更します。
* を `orgId` を組織の IMS 組織に送信します。

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

オプションで、次のその他のプロパティを設定できます [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 組織の実装要件に応じてコマンドを実行します。

+++

+++**4. JSON ペイロードを使用するようにコードロジックを更新する**

に依存しないように、Analytics 実装を変更します `AppMeasurement.js` または `s` オブジェクト。 代わりに、正しい形式の JavaScript オブジェクトに変数を設定し、Adobeに送信する際に JSON オブジェクトに変換します。 持つさま [データレイヤー](../../prepare/data-layer.md) サイトで値を設定すると、同じ値を引き続き参照できるので、非常に役立ちます。

データをAdobe Analyticsに送信するには、Web SDK ペイロードがを使用する必要があります `data.__adobe.analytics` このオブジェクト内で設定されたすべての analytics 変数を使用します。 このオブジェクト内の変数は、対応するAppMeasurement変数と同じ名前と形式を共有します。 例えば、 `products` 変数です。XDM の場合と同様に、個々のオブジェクトに分割しないでください。 代わりに、 `s.products` 変数：

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

最終的に、このペイロードには、必要な値と、に対するすべての参照が含まれます `s` 実装のオブジェクトが削除されました。 JavaScript が提供する任意のリソースを使用して、このペイロードオブジェクトを設定できます（個々の値を設定するドット表記を含む）。

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {analytics: {}}}};
dataObj.data.__adobe.analytics.pageName = window.document.title;
dataObj.data.__adobe.analytics.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{analytics:{...a}}}};
```

+++

+++**5. Web SDK を使用するメソッド呼び出しを更新します**

を呼び出すすべてのインスタンスを更新 [`s.t()`](../../vars/functions/t-method.md) および [`s.tl()`](../../vars/functions/tl-method.md)、それらを次の値に置き換えます。 [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) コマンド。 考慮すべきシナリオは次の 3 つです。

* **ページビュートラッキング**：ページビュートラッキング呼び出しを Web SDK に置き換えます `sendEvent` コマンド：

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **自動リンクトラッキング**：です [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) 設定プロパティはデフォルトで有効になっています。 Adobe Analyticsにデータを送信するための適切なリンクトラッキング変数が自動的に設定されます。 自動リンクトラッキングを無効にする場合は、このプロパティをに設定します。 `false` 内 [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) コマンド。

* **手動リンクトラッキング**:Web SDK には、pageview 呼び出しと非 pageview 呼び出しの間に別のコマンドはありません。 ペイロードオブジェクト内でその区別をしてください。

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.analytics.linkName = "Example custom link";
  dataObj.data.__adobe.analytics.linkType = "o";
  dataObj.data.__adobe.analytics.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6.変更の検証と公開**

AppMeasurementへの参照とフィールドへの参照をすべて削除したら、 `s` オブジェクトを作成し、変更を開発環境に公開して、新しい実装が機能することを検証します。 すべてが正しく動作することを検証したら、更新を実稼動環境に公開できます。

正しく移行された場合、 `AppMeasurement.js` はサイトで不要になり、このスクリプトへのすべての参照を削除できます。

+++

この時点で、Analytics 実装は Web SDK に完全に依存しており、将来Customer Journey Analyticsに移行するための準備が十分にあります。
