---
description: Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。
title: Activity Map の有効化
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 75d50a5b2cd31aa11df22fa6a271f7ab937a770c
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 85%

---


# Activity Map のアクティベートと有効化

Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。

## 手順 1.Activity Map のアクティベート {#update_code}

Activity Map モジュールは、AppMeasurement.js、Adobe Experience Platform タグおよび Web SDK（alloy.js）の一部です。**Web SDK バージョ ン2.15.0** 以降、または **Adobe Analytics タグ拡張機能 v1.90** 以降、または **AppMeasurement バージョン 1.6** 以降に更新しない限り、Activity Map データを収集できません。

+++Web SDK（Adobe Experience Platform タグ拡張機能）

メモ：現在、Web SDK は、個別のリンククリックイベントを記録して、Activity Map情報を収集します。 これは、内部リンクのActivity Map情報を記録するAppMeasurementとは異なり、後続のページ読み込みに内部リンク情報を含めます。 このため、Web SDK の収集の結果、追加のサーバーコールが発生します。 Web SDK の今後のリリースでは、基本的にAppMeasurementの動作と一致する、後続のヒットに関するActivity Map情報をパッケージ化するように Web SDK を設定できるようになります。

1. Adobe Experience Platform タグで、Analytics を実装するプロパティに移動します。
1. 次の下 [!UICONTROL 拡張機能] > [!UICONTROL Adobe Experience Platform Web SDK]を選択 **[!UICONTROL クリックデータ収集の有効化]** 以下でハイライト表示されているように。
1. 変更を加えてライブラリをビルドします。
1. ライブラリを実稼動環境に公開します。

![](assets/web_sdk.png)

**検証**

Developer Console の「ネットワーク」タブを使用た操作呼び出し：

1. サイトに開発用 Launch スクリプトを読み込みます。
1. 要素のクリック時に、「ネットワーク」タブで「/ee」を検索します。

   ![](assets/validation1.png)

Adobe Experience Platform Debugger：

1. [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) をダウンロードしてインストールします。
1. [!UICONTROL ログ]／[!UICONTROL Edge]／[!UICONTROL Edge に接続]に移動します。

   ![](assets/validation2.jpg)

**よくある質問（FAQ）**

* **「ネットワーク」タブでは、操作呼び出しが起動しません。**
収集呼び出しでのクリックデータ収集は、「/ee」または「collect?」でフィルタリングする必要があります。

* **収集呼び出しのペイロード表示がありません。**
収集呼び出しは、トラッキングが他のサイトへのナビゲーションに影響しないように設計されているので、ドキュメントのアンロード機能は収集呼び出しに適用できます。これはデータ収集には影響しませんが、ページで検証する必要がある場合は、それぞれの要素に「target = &quot;_blank」を追加します。その後、リンクが新しいタブで開きます。

* **PII の収集を無視するにはどうすればよいですか？**
&lt;&lt; on before link click send callback>> にそれぞれの条件を追加し、false を返してこれらの値を無視します。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)

  サンプルコード：

  ![](assets/sample-code.png)

+++

+++手動による Web SDK の実装

リンクトラッキングの実装方法と、クリックされた HTML 要素の `region` をキャプチャして Activity Map を有効にする方法について詳しくは、[リンクの追跡](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja)を参照してください。

>[!NOTE]
>
>現在、Web SDK でリンクトラッキングを有効にすると、顧客がページ間を移動した際にリンクイベントが送信されます。AppMeasurement の動作方法とは異なり、このイベントはアドビに送信される追加の課金対象ヒットとされる可能性があります。

+++

+++Analytics 拡張機能（Adobe Experience Platform タグ）

Adobe Experience Platform タグで、Analytics を実装するプロパティに移動します。[!UICONTROL 拡張機能のインストール]ダイアログで、「**[!UICONTROL Activity Map を使用]**」を選択します。

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. AppMeasurement 用の最新の JavaScript ライブラリをダウンロードします。
**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL すべての管理者]**／**[!UICONTROL Code Manager]** に移動します。
1. [これらの手順](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=ja)に従って実装してください。

+++

## 手順 2.Activity Map レポートを有効にする {#enable}

レポートスイートレベルで Activity Map レポートを有効にする必要があります。

1. Adobe Analytics にログインし、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動してレポートスイートを選択し、**[!UICONTROL 設定を編集]**／**[!UICONTROL Activity Map]**／**[!UICONTROL Activity Map レポート]** に移動します。

1. リンクデータが Activity Map レポートに収集されます。有効化をおこなうには、まず「**[!UICONTROL Activity Map レポートを有効にする]**」をクリックして変数を有効にする必要があります。

   この手順により、データの収集が必要な Analytics のディメンションがすべて追加されます。

   ![](assets/enable.png)

1. 約 1 時間後に、[Activity Map ページレポート](/help/analyze/activity-map/activitymap-reporting-analytics.md)を確認すると、ユーザーがリンクをクリックしたページがすべて表示されます。

## 手順 3.ユーザーを [!UICONTROL Activity Map アクセス]製品プロファイルに追加 {#add_users}

1. 「**[!UICONTROL ユーザーをグループに追加]**」をクリックします。

   [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview) の製品プロファイルページが表示されます。

1. [!UICONTROL Activity Map アクセス]製品プロファイルをまだ作成していない場合は、今すぐ作成します。このプロファイルに必要な権限項目は、[!UICONTROL Analytics ツール]／[!UICONTROL Activity Map] および [!UICONTROL Analytics ツール]／[!UICONTROL セグメント公開]です。

1. 製品プロファイルにユーザーを追加します。これで、ユーザーは、**[!UICONTROL Adobe Analytics]**／**[!UICONTROL ツール]**／**[!UICONTROL Activity Map]** から Activity Map をダウンロードできます。

