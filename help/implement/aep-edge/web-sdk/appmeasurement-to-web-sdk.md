---
title: AppMeasurementから Web SDKへの移行
description: Adobe Analytics実装をAppMeasurement JavaScript ライブラリから Web SDK JavaScript ライブラリに更新します。
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 05690cc8c1ea0364cbab86f35666df1cc1b13e69
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 7%

---

# AppMeasurementから Web SDKへの移行

この実装パスには、AppMeasurement実装から Web SDK JavaScript ライブラリ実装に移行するための系統的な移行アプローチが含まれます。 その他の実装パスについては、次の別のページで説明しています。

* [Analytics 拡張機能を web SDK拡張機能に &#x200B;](analytics-extension-to-web-sdk.md):Adobe Analytics タグ拡張機能から Web SDK タグ拡張機能にスムーズかつ系統的なアプローチで移行します。 このアプローチにより、Customer Journey AnalyticsなどのAdobe Experience Platform サービスを使用する準備が整うまで XDM を使用する必要がなくなります。 データをAdobeに送信するには、`data` オブジェクトの代わりに `xdm` オブジェクトを使用します。
* [Web SDK JavaScript ライブラリ &#x200B;](web-sdk-javascript-library.md):Web SDK JavaScript ライブラリ（`alloy.js`）を使用した新規の Web SDK インストール。 タグ UI を使用する代わりに、自分で実装を管理します。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。
* [Web SDK タグ拡張機能 &#x200B;](web-sdk-tag-extension.md):Adobe Experience Platform Data Collection のタグを使用して実装を管理する、新規の Web SDK インストール。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。

## この実装パスのメリットとデメリット

この移行アプローチを使用すると、メリットとデメリットの両方が生じます。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックへの最小限の変更で、既存のデータレイヤーとコードを使用できます。</li><li>**スキーマは必要ありません**:Web SDKへの移行のこの段階では、XDM スキーマは必要ありません。 代わりに、`data` オブジェクトにデータを入力し、Adobe Analyticsにデータを直接送信することができます。 Web SDKへの移行が完了したら、組織のスキーマを作成し、データストリームマッピングを使用して該当する XDM フィールドに値を入力できます。 移行プロセスのこの段階でスキーマが必要だった場合、組織はAdobe Analytics XDM スキーマの使用を強制されます。 このスキーマを使用すると、組織が今後独自のスキーマを使用するのが難しくなります。</li></ul> | <ul><li>**実装の変更には、開発者の介入が必要です**:web SDKの実装を変更する場合は、開発チームと協力してサイトのコードを編集する必要があります。 [Web SDK タグ拡張機能に移行する &#x200B;](analytics-extension-to-web-sdk.md) アプローチでは、この欠点を回避できます。</li><li>**実装の技術的負債**：このアプローチは既存の実装を変更した形式を使用するので、実装ロジックを追跡し、必要に応じて将来変更を実行するのは難しい場合があります。</li><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。このアクションでは、`data` オブジェクトのすべてのフィールドが、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリである必要があります。 このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li></ul> |

Adobeでは、次のシナリオでこの実装パスを使用することをお勧めします。

* 既存の実装がある場合は、Adobe Analytics AppMeasurement JavaScript ライブラリを使用します。 Adobe Analytics タグ拡張機能を使用した実装がある場合は、代わりに [Adobe Analytics タグ拡張機能から web SDK タグ拡張機能に移行 &#x200B;](analytics-extension-to-web-sdk.md) に従います。
* 今後Customer Journey Analyticsを使用するが、Analytics 実装を web SDK実装に最初から置き換える必要がない。 Web SDK上で実装をゼロから置き換えることは最も労力を要しますが、最も実行可能な長期的な実装アーキテクチャも提供します。 Web SDKのクリーンな実装に取り組む気がある場合は、『Customer Journey Analytics ユーザーガイド』の [Adobe Experience Platform Web SDKを使用したデータの取り込み &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) を参照してください。

## Web SDKへの移行に必要な手順

以下の手順には、取り組むべき具体的な目標が含まれています。 各手順をクリックすると、実行方法に関する詳細な手順が表示されます。

+++**1.データストリームの作成と設定**

Adobe Experience Platform Data Collection にデータストリームを作成します。 このデータストリームにデータを送信すると、データがAdobe Analyticsに転送されます。 今後、この同じデータストリームがCustomer Journey Analyticsにデータを転送します。

1. [experience.adobe.com](https://experience.adobe.com) に移動し、資格情報を使用してログインします。
1. 右上のホームページまたは製品セレクターを使用して、**[!UICONTROL データ収集]** に移動します。
1. 左側のナビゲーションで、「**[!UICONTROL データストリーム]**」を選択します。
1. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。
1. 目的の名前を入力し、「**[!UICONTROL 保存]**」を選択します。
1. データストリームを作成したら、「**[!UICONTROL サービスを追加]**」を選択します。
1. サービス ドロップダウンメニューで、「**[!UICONTROL Adobe Analytics]**」を選択します。
1. 分析データを現在送信しているサイトと同じレポートスイート ID を入力します。 「**[!UICONTROL 保存]**」をクリックします。

![Adobe Analytics サービスの追加 &#x200B;](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

これで、データストリームがデータを受け取り、Adobe Analyticsに渡す準備が整いました。 データストリーム ID に注意してください。この ID は、コードで web SDKを設定する際に必要になるからです。

+++

+++**2. Web SDK JavaScript ライブラリをインストール** ます。

メソッド呼び出しを使用できるように、`alloy.js` の最新バージョンを参照します。 詳細および使用するコードブロックについては、[JavaScript ライブラリを使用した web SDKのインストール &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/install/library) を参照してください。

+++

+++**3.Web SDKを設定する**

Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) コマンドを使用して、前の手順で作成したデータストリームを指すように実装を設定します。 `configure` コマンドは、ライブラリのインストールコードと一緒に含めることができるように、すべてのページで設定する必要があります。

Web SDK [`datastreamId` コマンド内で &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/datastreamid) [`orgId` および &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid)`configure` プロパティを使用します。

* `datastreamId` を、前の手順で取得したデータストリーム ID に設定します。
* 組織の IMS 組織に `orgId` を設定します。

```js
alloy("configure", {
    datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
    orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

組織の実装要件に応じて、[`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) コマンドで他のプロパティをオプションで設定できます。

+++

+++**4. JSON ペイロードを使用するようにコードロジックを更新し** す。

`AppMeasurement.js` や `s` オブジェクトに依存しないように、Analytics 実装を変更します。 代わりに、正しい形式のJavaScript オブジェクトに変数を設定し、Adobeに送信する際に JSON オブジェクトに変換します。 サイトに [&#x200B; データレイヤー &#x200B;](../../prepare/data-layer.md) があると、値を設定する際に非常に役立ちます。これは、同じ値を引き続き参照できるからです。

データをAdobe Analyticsに送信するには、web SDK ペイロードは、このオブジェクト内で設定されたすべての分析変数と `data.__adobe.analytics` を使用する必要があります。 このオブジェクト内の変数は、対応するAppMeasurement変数と同じ名前および形式を共有します。 例えば、`products` 変数を設定する場合、XDM の場合とは異なり、変数を個々のオブジェクトに分割しないでください。 代わりに、`s.products` の変数を設定した場合に、文字列として正確に含めます。

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

最終的に、このペイロードには、必要な値がすべて含まれ、実装内の `s` オブジェクトへのすべての参照が削除されます。 JavaScriptが提供する任意のリソースを使用して、このペイロードオブジェクトを設定できます（個々の値を設定するドット表記を含む）。

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

+++**5. Web SDKを使用するためのメソッド呼び出しを更新します**

[`s.t()`](../../vars/functions/t-method.md) および [`s.tl()`](../../vars/functions/tl-method.md) を呼び出すすべてのインスタンスを更新し、[`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) コマンドで置き換えます。 考慮すべきシナリオは次の 3 つです。

* **ページビュートラッキング**：ページビュートラッキング呼び出しを Web SDK `sendEvent` コマンドに置き換えます。

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **自動リンクトラッキング**:[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) 設定プロパティは、デフォルトで有効になっています。 Adobe Analyticsにデータを送信するための適切なリンクトラッキング変数が自動的に設定されます。 自動リンクトラッキングを無効にする場合は、`false`[`configure` コマンド内でこのプロパティを &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) に設定します。

* **手動のリンクトラッキング**:web SDKには、pageview 呼び出しと非 pageview 呼び出しの間に別のコマンドはありません。 ペイロードオブジェクト内でその区別をしてください。

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

+++**6.変更を検証して公開する**

AppMeasurementおよび `s` オブジェクトへの参照をすべて削除したら、変更内容を開発環境に公開して、新しい実装が機能することを検証します。 すべてが正しく動作することを検証したら、更新を実稼動環境に公開できます。

正しく移行されると、`AppMeasurement.js` はサイトで不要になり、このスクリプトへのすべての参照を削除できます。

+++

この時点で、Analytics 実装は完全に Web SDK上にあり、将来Customer Journey Analyticsに移行する準備が十分にあります。
