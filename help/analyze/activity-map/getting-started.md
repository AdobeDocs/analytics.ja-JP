---
title: Activity Map の基本を学ぶ
description: Activity Map のオーバーレイとディメンションの使用方法について説明します。
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
TQID: https://experienceleague.adobe.com/Wt30b3LTZWyzAQFOKqkqBdWH2Ifatq5FLp-Z0z7nktA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889beid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: af860ea2bf90f0f25bfb95b943d9ae11bf808028
workflow-type: tm+mt
source-wordcount: 933
ht-degree: 97%

---

# Activity Map の基本を学ぶ

Adobe Analytics の Activity Map は、次の 4 つの主な要素で構成されています。

* **レポートスイート設定**：レポートスイート設定で Activity Map を有効にする必要があります。 有効にした際、レポートスイートは Activity Map のディメンションと指標用にいくつかの予約変数を作成します。
* **実装**：web サイトまたはプロパティで Activity Map データを収集します。 データ収集方法をカスタマイズすることで、レポートの品質とエクスペリエンスを向上させることができます。
* **Workspace のディメンションと指標**：実装が正しく設定されている場合、Analysis Workspace で Activity Map のディメンションと指標を使用できます。
* **オーバーレイ**：アドビは、web サイトのコンテキストで Activity Map データを表示するためのブラウザー拡張機能を提供しています。 この機能は、Web SDK 実装では使用できません。

## レポートスイート設定の有効化

データの収集を開始する前に、レポートスイートで Activity Map レポートを有効にする必要があります。 実装により、Activity Map レポートが有効になっていない状態でレポートスイートに Activity Map データが送信された場合、Activity Map データはヒットに含まれません。

**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／レポートスイートを選択／**[!UICONTROL 設定を編集]**／**[!UICONTROL Activity Map]**／**[!UICONTROL Activity Map レポート]**／**[!UICONTROL Activity Map レポートを有効にする]**

Activity Map レポートを有効にすると、複数のバックエンド予約変数が作成されます。 詳しくは、Adobe Analytics 管理ガイドの [Activity Map レポート](/help/admin/tools/manage-rs/edit-settings/activity-map.md)を参照してください。

## コードのインストール

Activity Map データをアドビに送信するには、実装を正しく設定する必要があります。 Adobe Analytics が Web SDK を使用して実装されている場合、オーバーレイブラウザー拡張機能は使用できません。

+++Web SDK タグ拡張機能

Activity Map のデータ収集には、**[!UICONTROL Adobe Experience Platform Web SDK]** 拡張機能 v2.23 以降が必要です。 拡張機能バージョン v2.16 までは、サポートが制限されています。 これらの以前の拡張機能バージョンでは、Activity Map データが他のデータとは別のイベントで送信されます。 この追加イベントにより、Adobe Analytics または Adobe Experience Platform に送信されるヒットの数が増加します。

**[!UICONTROL クリックデータ収集]**&#x200B;設定は、Activity Map データ収集を処理し、通常はデフォルトで有効になっています。 拡張機能の設定で有効になっていることを確認できます。

1. Adobe IDの資格情報を使用して[Adobe CX Enterprise](https://experience.adobe.com)にログインします。
1. クイックアクセスメニューまたは右上の製品セレクターで「**[!UICONTROL データ収集]**」を選択します。
1. 左側のナビゲーションメニューの「**[!UICONTROL タグ]**」を選択します。
1. 編集する目的のタグを選択します。
1. 左側のナビゲーションメニューの「**[!UICONTROL 拡張機能]**」を選択します。
1. インストールされている拡張機能のリストで「**[!UICONTROL Adobe Experience Platform Web SDK]**」を選択し、右側の「**[!UICONTROL 設定]**」を選択します。
1. 「[!UICONTROL データ収集]」というラベルの付いたセクションを見つけて、「**[!UICONTROL クリックデータ収集を有効にする]**」チェックボックスがオンになっていることを確認します。
1. 「**[!UICONTROL 保存]**」を選択します。
1. 必要に応じて、ライブラリに変更を作成し、実稼動環境に公開します。

詳しくは、[Web SDK タグ拡張機能の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection)を参照してください。

+++

+++Web SDK JavaScript ライブラリ（`alloy.js`）

Activity Map のデータ収集には、Web SDK JavaScript ライブラリ v2.20 以降が必要です。 バージョン 2.15 までのライブラリでは、サポートが制限されています。 これらの以前のライブラリバージョンでは、Activity Map データが他のデータとは別のイベントで送信されます。 この追加イベントにより、Adobe Analytics または Adobe Experience Platform に送信されるヒットの数が増加します。

Web SDK 設定変数 [`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) は、Activity Map データの自動収集を処理します。 明示的に無効にしない限り、デフォルトで有効になっています。

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Adobe Analytics タグ拡張機能

**[!UICONTROL Activity Map を使用]**&#x200B;設定は、Activity Map データ収集を処理し、通常はデフォルトで有効になっています。 これは、すべてのタグ拡張機能 v1.9.0 以降で使用できます。 拡張機能の設定で有効になっていることを確認できます。

1. Adobe IDの資格情報を使用して[Adobe CX Enterprise](https://experience.adobe.com)にログインします。
1. クイックアクセスメニューまたは右上の製品セレクターで「**[!UICONTROL データ収集]**」を選択します。
1. 左側のナビゲーションメニューの「**[!UICONTROL タグ]**」を選択します。
1. 編集する目的のタグを選択します。
1. 左側のナビゲーションメニューの「**[!UICONTROL 拡張機能]**」を選択します。
1. インストールされている拡張機能のリストで「**[!UICONTROL Adobe Analytics]**」を選択し、右側の「**[!UICONTROL 設定]**」を選択します。
1. 「**[!UICONTROL Activity Map を使用]**」チェックボックスがオンになっていることを確認します。
1. 「**[!UICONTROL 保存]**」を選択します。
1. 必要に応じて、ライブラリに変更を作成し、実稼動環境に公開します。

詳しくは、[Adobe Analytics 拡張機能の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/analytics/overview)を参照してください。

+++

+++Adobe Analytics JavaScript ライブラリ（`AppMeasurement.js`）

Activity Map モジュールは、Activity Map データの収集を処理し、すべての AppMeasurement ライブラリ v1.6 以降に含まれています。 `AppMeasurement.js` ファイルを調べると、これが含まれていることを確認できます。

1. GitHub の[最新の Adobe Analytics AppMeasurement リリース](https://github.com/adobe/appmeasurement/releases/latest)に移動します。
1. 圧縮された AppMeasurement ライブラリファイルをダウンロードし、内部に含まれている `AppMeasurement.js` を開きます。
1. Activity Map モジュールは、このファイルの上部付近に含まれています。 このモジュールが、サイトで使用する AppMeasurement ライブラリに含まれていることを確認します。

+++

## 使用可能なディメンション

レポートスイートと実装の両方で Activity Map が有効になっている場合は、Analysis Workspace で次のディメンションの使用を開始できます。

* [[!UICONTROL Activity Map リンク]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map 地域]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map ページ]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Activity Map 地域別リンク]](/help/components/dimensions/activity-map-link-by-region.md)

## ブラウザー拡張機能またはアドオンのダウンロードとインストール

Analysis Workspace で使用できるディメンションに加えて、Activity Map データを web サイト上のオーバーレイとして表示することもできます。 このオーバーレイを表示するには、Activity Map ブラウザー拡張機能またはアドオンをダウンロードおよびインストールします。

**[!UICONTROL ツール]**／**[!UICONTROL Activity Map]**／**[!UICONTROL Activity Map をダウンロード]**

このリンクをクリックすると、ブラウザーでサポートされている拡張機能またはアドオンの Marketplace に移動してインストールできます。 インストールが完了すると、ブラウザーの右上に拡張機能またはアドオンが表示され、ログインしてオーバーレイを有効にすることができます。
