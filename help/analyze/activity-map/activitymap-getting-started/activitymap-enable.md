---
description: Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。
title: Activity Map の有効化
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 7f7f6347561d51671bbcb20959895178f3428314
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 40%

---


# 「アクティブ化して有効化」Activity Map

Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。

## 手順 1.有効化Activity Map {#update_code}

Activity Mapモジュールは、AppMeasurement.js、Adobe Experience Platformタグおよび Web SDK(alloy.js) の一部です。 Activity Mapデータは、 **Web SDK バージョン2.15.0** 以上、または **Adobe Analytics tags 拡張機能 v1.90** 以上、または **AppMeasurementバージョン 1.6** 以上

+++Web SDK （Tags 拡張機能）

Adobe Experience Platformタグで、Analytics を実装するプロパティに移動します。 の下 [!UICONTROL 拡張機能] -> [!UICONTROL Adobe Experience Platform Web SDK]を選択します。 **[!UICONTROL クリックデータの収集を有効にする]** 以下に示すように。 次に、変更を加えてライブラリを構築し、実稼動環境に公開します。

![](assets/web_sdk.png)

+++

+++手動での Web SDK の実装

詳しくは、 [リンクを追跡](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja) リンクトラッキングの実装方法と、 `region` クリックされたHTML要素の

>[!NOTE]
>
>現在、Web SDK でリンクトラッキングを有効にすると、顧客がページ間を移動した際にリンクイベントが送信されます。AppMeasurement の動作方法とは異なり、このイベントはアドビに送信される追加の課金対象ヒットとされる可能性があります。

+++

+++Analytics 拡張機能 (Adobe Experience Platformタグ )

Adobe Experience Platformタグで、Analytics を実装するプロパティに移動します。 Adobe Analytics の [!UICONTROL 拡張機能のインストール] ダイアログ、選択 **[!UICONTROL 使用Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. AppMeasurement用の最新の JavaScript ライブラリをダウンロードします。
に移動します。 **[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]** > **[!UICONTROL コードマネージャー]**.
1. 次の手順で実装します。 [これらの手順](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=ja).

+++

## 手順 2.Activity Map レポートを有効にする {#enable}

まず、レポートスイートレベルでActivity Mapレポートを有効にする必要があります。

1. Adobe Analytics にログインし、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動してレポートスイートを選択し、**[!UICONTROL 設定を編集]**／**[!UICONTROL Activity Map]**／**[!UICONTROL Activity Map レポート]** に移動します。

1. リンクデータが Activity Map レポートに収集されます。有効化をおこなうには、まず「**[!UICONTROL Activity Map レポートを有効にする]**」をクリックして変数を有効にする必要があります。

   この手順により、データの収集が必要な Analytics のディメンションがすべて追加されます。

   ![](assets/enable.png)

1. 約 1 時間後に、[Activity Map ページレポート](/help/analyze/activity-map/activitymap-reporting-analytics.md)を確認すると、ユーザーがリンクをクリックしたページがすべて表示されます。

## 手順 3.ユーザーの追加先 [!UICONTROL Activity Mapアクセス] 製品プロファイル {#add_users}

1. 「**[!UICONTROL ユーザーをグループに追加]**」をクリックします。

   これにより、 [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. まだ [!UICONTROL Activity Mapアクセス] 製品プロファイルに移動します。 このプロファイルに必要な権限項目は次のとおりです [!UICONTROL Analytics ツール] > [!UICONTROL Activity Map] および [!UICONTROL Analytics ツール] > [!UICONTROL セグメント公開].

1. 製品プロファイルにユーザーを追加します。 これにより、ユーザーは、  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL ツール]** > **[!UICONTROL ActivityMap]** .

