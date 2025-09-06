---
title: Activity Mapの概要
description: Activity Mapのオーバーレイと寸法の使用を開始します。
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Activity Mapの概要

Adobe AnalyticsのActivity Mapは、次の 4 つの主な要素で構成されます。

* **レポートスイート設定**：レポートスイート設定でActivity Mapを有効にする必要があります。 有効になっている場合、レポートスイートはActivity Mapのディメンションおよび指標用にいくつかの予約変数を作成します。
* **実装**:Web サイトまたはプロパティでActivity Map データを収集します。 データの収集方法をカスタマイズすると、レポートの品質とエクスペリエンスが向上します。
* **Workspaceのディメンションと指標**：実装が正しく設定されている場合、Analysis WorkspaceでActivity Mapのディメンションと指標を使用できます。
* **オーバーレイ**:Adobeは、web サイトのコンテキストでActivity Map データを表示するためのブラウザー拡張機能を提供します。

## レポートスイート設定の有効化

データの収集を開始するには、レポートスイートでActivity Map レポートが有効になっている必要があります。 Activity Map レポートを有効にせずに、実装からレポートスイートにActivity Map データが送信される場合、Activity Map データはヒットに含まれません。

**[!UICONTROL 管理者]**/**[!UICONTROL レポートスイート]**/レポートスイートを選択/**[!UICONTROL 設定を編集]**/**[!UICONTROL Activity Map]**/**[!UICONTROL Activity Map レポート]**/**[!UICONTROL Activity Map レポートを有効にする]**

Activity Map レポートを有効にすると、複数のバックエンド予約変数が作成されます。 詳しくは、『Adobe Analytics管理ガイド』の [0&rbrace;Activity Map レポート &rbrace; を参照してください。](/help/admin/tools/manage-rs/edit-settings/activity-map.md)

## コードのインストール

Activity Map データをAdobeに送信するように実装を正しく設定する必要があります。

+++Web SDK タグ拡張機能

Activity Mapのデータ収集には、**[!UICONTROL Adobe Experience Platform Web SDK]** 拡張機能 v2.23 以降が必要です。 v2.16 までの拡張機能バージョンのサポートは限られています。 これらの以前のバージョンの拡張機能では、Activity Mapのデータが、他のデータとは別のイベントに送信されます。 この追加のイベントにより、Adobe AnalyticsまたはAdobe Experience Platformに送信するヒット数が増加します。

**[!UICONTROL クリックデータ収集]** 設定は、Activity Mapのデータ収集を処理し、通常はデフォルトで有効になっています。 拡張機能の設定で有効になっていることを確認できます。

1. [experience.adobe.com](https://experience.adobe.com) にログインします
1. クイックアクセスメニューの **[!UICONTROL データ収集]** を選択するか、右上の製品セレクターを選択します。
1. 左側のナビゲーションメニューで **[!UICONTROL タグ]** を選択します。
1. 編集するタグを選択します。
1. 左側のナビゲーションメニューで **[!UICONTROL 拡張機能]** を選択します。
1. インストールされている拡張機能のリストで **[!UICONTROL 0&rbrace;Adobe Experience Platform Web SDK&rbrace; を選択し、右側の]** 設定 **[!UICONTROL を選択します。]**
1. [!UICONTROL &#x200B; データ収集 &#x200B;] というラベルの付いたセクションを見つけ、チェックボックス **[!UICONTROL クリックデータ収集を有効にする]** が有効になっていることを確認します。
1. 「**[!UICONTROL 保存]**」を選択します。
1. 必要に応じて、変更をライブラリにビルドし、変更を実稼動環境に公開します。

詳しくは [Web SDK タグ拡張機能の設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) を参照してください。

+++

+++Web SDK JavaScript ライブラリ（`alloy.js`）

Activity Mapのデータ収集には、Web SDK JavaScript ライブラリ v2.20 以降が必要です。 ライブラリのバージョンが v2.15 以下の場合、サポートは制限されます。 これらの以前のバージョンのライブラリでは、Activity Mapのデータが、残りのデータとは別のイベントに送信されます。 この追加のイベントにより、Adobe AnalyticsまたはAdobe Experience Platformに送信するヒット数が増加します。

Activity Map データの自動収集を処理す [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)Web SDK設定変数。 明示的に無効にしない限り、このモードはデフォルトで有効になっています。

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Adobe Analytics タグ拡張機能

**[!UICONTROL Activity Mapを使用]** 設定は、Activity Mapのデータ収集を処理し、通常はデフォルトで有効になっています。 これは、すべてのタグ拡張機能 v1.9.0 以降で使用できます。 拡張機能の設定で有効になっていることを確認できます。

1. [experience.adobe.com](https://experience.adobe.com) にログインします
1. クイックアクセスメニューの **[!UICONTROL データ収集]** を選択するか、右上の製品セレクターを選択します。
1. 左側のナビゲーションメニューで **[!UICONTROL タグ]** を選択します。
1. 編集するタグを選択します。
1. 左側のナビゲーションメニューで **[!UICONTROL 拡張機能]** を選択します。
1. インストールされている拡張機能のリストで **[!UICONTROL 0&rbrace;Adobe Analytics&rbrace; を選択し、右側の]** 設定 **[!UICONTROL を選択します。]**
1. 「Activity Mapを使用 **[!UICONTROL チェックボックスが有効になってい]** ことを確認します。
1. 「**[!UICONTROL 保存]**」を選択します。
1. 必要に応じて、変更をライブラリにビルドし、変更を実稼動環境に公開します。

詳しくは、[Adobe Analytics拡張機能の概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) を参照してください。

+++

+++Adobe Analytics JavaScript ライブラリ（`AppMeasurement.js`）

Activity Map モジュールは、Activity Mapのデータ収集を処理し、すべてのAppMeasurement ライブラリ v1.6 以降に含まれています。 `AppMeasurement.js` ファイルを調べると、そのファイルがインクルードされているかどうかを確認できます。

1. GitHub の [ 最新のAdobe Analytics AppMeasurement リリース ](https://github.com/adobe/appmeasurement/releases/latest) に移動します。
1. 圧縮されたAppMeasurement ライブラリファイルをダウンロードし、内に含まれているファイル `AppMeasurement.js` 開きます。
1. Activity Map モジュールは、このファイルの上部付近に含まれています。 このモジュールが、サイトで使用するAppMeasurement ライブラリに含まれていることを確認します。

+++

## 使用可能なディメンション

レポートスイートと実装の両方でActivity Mapが有効になっている場合、Analysis Workspaceで次のディメンションの使用を開始できます。

* [[!UICONTROL Activity Map リンク &#x200B;]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map地域 &#x200B;]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Mapページ &#x200B;]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Activity Map リンク （地域別） &#x200B;]](/help/components/dimensions/activity-map-link-by-region.md)

## ブラウザー拡張機能またはアドオンのダウンロードとインストール

Analysis Workspaceで使用できるディメンションに加えて、Activity Map データを web サイト上にオーバーレイとして表示することもできます。 このオーバーレイを表示するには、Activity Map ブラウザー拡張機能またはアドオンをダウンロードしてインストールします。

**[!UICONTROL ツール]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Mapのダウンロード]**

このリンクをクリックすると、ブラウザーでサポートされている拡張機能またはアドオンの Marketplace に移動してインストールできます。 インストールが完了すると、ブラウザーの右上に拡張機能またはアドオンが表示され、ログインしてオーバーレイを有効にすることができます。
