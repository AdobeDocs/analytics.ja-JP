---
title: Activity Map使用の手引き
description: Activity Mapのオーバーレイと寸法の使用を開始します。
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# Activity Map使用の手引き

Adobe AnalyticsのActivity Mapは、次の 4 つの主要な要素で構成されます。

* **レポートスイートの設定**：レポートスイート設定でActivity Mapを有効にする必要があります。 有効にすると、レポートスイートは、Activity Mapディメンションおよび指標用に複数の予約変数を作成します。
* **実装**:Web サイトまたはプロパティでActivity Mapデータを収集します。 データの収集方法をカスタマイズすると、レポートの品質とエクスペリエンスが向上します。
* **Workspaceのディメンションと指標**：実装が正しく設定されている場合、Analysis WorkspaceでActivity Mapのディメンションと指標を使用できます。
* **オーバーレイ**:Adobeは、web サイトのコンテキストでActivity Mapデータを表示するためのブラウザー拡張機能を提供します。

## レポートスイート設定の有効化

データの収集を開始するには、レポートスイートでActivity Mapレポートが有効になっている必要があります。 Activity Mapレポートを有効にせずに、実装からレポートスイートにActivity Mapデータが送信された場合、ヒットにActivity Mapデータは含まれません。

**[!UICONTROL 管理者]**/**[!UICONTROL レポートスイート]**/レポートスイートを選択/**[!UICONTROL 設定を編集]**/**[!UICONTROL Activity Map]**/**[!UICONTROL Activity Mapレポート]**/**[!UICONTROL Activity Mapレポートを有効にする]**

Activity Mapレポートを有効にすると、複数のバックエンド予約変数が作成されます。 詳しくは、Adobe Analytics管理ガイドの [&#128279;](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)0&rbrace;Activity Mapレポート &rbrace; を参照してください。

## コードのインストール

Activity MapデータをAdobeに送信するように実装を正しく設定する必要があります。

+++Web SDK タグ拡張機能

Activity Mapデータ収集には、**[!UICONTROL Adobe Experience Platform Web SDK]** 拡張機能 v2.23 以降が必要です。 v2.16 までの拡張機能バージョンのサポートは限られています。 これらの以前のバージョンの拡張機能では、Activity Mapデータが、他のデータとは別のイベントに送信されます。 この追加のイベントにより、Adobe AnalyticsまたはAdobe Experience Platformに送信するヒット数が増加します。

**[!UICONTROL クリックデータ収集]** 設定は、Activity Mapデータ収集を処理し、通常はデフォルトで有効になっています。 拡張機能の設定で有効になっていることを確認できます。

1. [experience.adobe.com](https://experience.adobe.com) にログインします
1. クイックアクセスメニューの **[!UICONTROL データ収集]** を選択するか、右上の製品セレクターを選択します。
1. 左側のナビゲーションメニューで **[!UICONTROL タグ]** を選択します。
1. 編集するタグを選択します。
1. 左側のナビゲーションメニューで **[!UICONTROL 拡張機能]** を選択します。
1. インストールされている拡張機能のリストで **0&rbrace;Adobe Experience Platform Web SDK&rbrace; を選択し、右側の**&#x200B;[!UICONTROL &#x200B; 設定 &#x200B;]&#x200B;**を選択します。**
1. [!UICONTROL &#x200B; データ収集 &#x200B;] というラベルの付いたセクションを見つけ、チェックボックス **[!UICONTROL クリックデータ収集を有効にする]** が有効になっていることを確認します。
1. 「**[!UICONTROL 保存]**」を選択します。
1. 必要に応じて、変更をライブラリにビルドし、変更を実稼動環境に公開します。

詳しくは、[Web SDK タグ拡張機能の設定 ](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) を参照してください。

+++

+++Web SDK JavaScript ライブラリ（`alloy.js`）

Activity Mapデータ収集には、Web SDK JavaScript ライブラリ v2.20 以降が必要です。 ライブラリのバージョンが v2.15 以下の場合、サポートは制限されます。 これらの以前のライブラリバージョンでは、Activity Mapデータが、残りのデータとは別のイベントで送信されます。 この追加のイベントにより、Adobe AnalyticsまたはAdobe Experience Platformに送信するヒット数が増加します。

Web SDK 設定変数 [`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) は、Activity Mapデータの自動収集を処理します。 明示的に無効にしない限り、このモードはデフォルトで有効になっています。

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
1. インストールされている拡張機能のリストで **0&rbrace;Adobe Analytics&rbrace; を選択し、右側の**&#x200B;[!UICONTROL &#x200B; 設定 &#x200B;]&#x200B;**を選択します。**
1. チェックボックス **[!UICONTROL Activity Mapを使用]** が有効になっていることを確認します。
1. 「**[!UICONTROL 保存]**」を選択します。
1. 必要に応じて、変更をライブラリにビルドし、変更を実稼動環境に公開します。

詳しくは、[Adobe Analytics拡張機能の概要 ](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/analytics/overview) を参照してください。

+++

+++Adobe Analytics JavaScript ライブラリ（`AppMeasurement.js`）

Activity Mapモジュールは、Activity Mapデータの収集を処理し、すべてのAppMeasurementライブラリ v1.6 以降に含まれています。 `AppMeasurement.js` ファイルを調べると、そのファイルがインクルードされているかどうかを確認できます。

1. GitHub の [ 最新のAdobe Analytics AppMeasurementリリース ](https://github.com/adobe/appmeasurement/releases/latest) に移動します。
1. 圧縮されたAppMeasurementライブラリファイルをダウンロードし、内に含まれているファイル `AppMeasurement.js` 開きます。
1. Activity Mapモジュールは、このファイルの上部付近に含まれています。 このモジュールが、サイトで使用するAppMeasurementライブラリに含まれていることを確認します。

+++

## 使用可能なディメンション

レポートスイートと実装の両方でActivity Mapが有効になっている場合、Analysis Workspaceで次のディメンションの使用を開始できます。

* [[!UICONTROL Activity Mapリンク &#x200B;]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map地域 &#x200B;]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Mapページ &#x200B;]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Activity Mapリンク （地域別） &#x200B;]](/help/components/dimensions/activity-map-link-by-region.md)

## ブラウザー拡張機能またはアドオンのダウンロードとインストール

Analysis Workspaceで使用できるディメンションに加えて、Activity Mapデータを web サイト上にオーバーレイとして表示することもできます。 このオーバーレイを表示するには、Activity Mapブラウザー拡張機能またはアドオンをダウンロードしてインストールしてください。

**[!UICONTROL ツール]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Mapのダウンロード]**

このリンクをクリックすると、ブラウザーでサポートされている拡張機能またはアドオンの Marketplace に移動してインストールできます。 インストールが完了すると、ブラウザーの右上に拡張機能またはアドオンが表示され、ログインしてオーバーレイを有効にすることができます。
