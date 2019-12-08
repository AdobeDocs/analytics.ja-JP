---
description: Adobe Analytics 実装を初めて実装する場合について説明します。
keywords: Getting Started
subtopic: Analysis Workspace
title: 簡易実装モーダル
topic: Reports and analytics
uuid: 6fad2c1f-476c-4985-90df-7c222e751ddc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 簡易実装モーダル

Adobe Analytics 実装を初めて実装する場合について説明します。

<!-- 

<p>https://activation.adobedtm.com/index.php?redirected=1 </p>

 -->

新規ユーザーは、この *`Getting Started with Adobe Analytics`* セットアップモーダルを使用して、最初の [!DNL Analytics] レポートスイート（データリポジトリ）をすばやく作成できます。次に、[!DNL Analytics] を使用して [!DNL Dynamic Tag Management] コードをデプロイできます。

[!DNL Dynamic Tag Management] では、毎回サイトを変更することなく、Adobe Analytics 実装を管理できます。モバイルアプリを実装している場合、アプリから価値あるデータを収集し始めるために必要な SDK を入手できます。

ここでは以下の処理をおこなえます。

* 最初の[レポートスイート](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html)をすばやく作成する。
* デプロイ [!DNL Analytics] とIDサー [ビス](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

* 基本ページレベルのデータでレポートを実行する。

> [!NOTE] 開始する前に、AnalyticsがAdobe Experience Cloud [](https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html) （ソリューションプロビジョニングプロセス）で有効になっていることを確認します。 Enterprise Dashboard の Analytics にログインするための招待メールを受け取った場合は、この前提条件を完了しています。

**シンプル化された実装モーダルを実行するには**

1. Log in to the [!DNL Adobe Experience Cloud] ( [experiencecloud.adobe.com](https://experiencecloud.adobe.com)).

   [!DNL Analytics] にアクセスする際に、レポートスイートがあるかどうかをシステムが識別します。ない場合、[!UICONTROL Adobe Analytics 使用の手引き]ページが表示されます。

   ![](assets/analytics-implementation-rs-wizard.png)

   代わりに、**[!UICONTROL ヘルプ]**／**[!UICONTROL Adobe Analytics へようこそ]**&#x200B;をクリックして、[!DNL Analytics] でこのセットアップを実行できます。

1. ビジネスに関する次の基本情報を指定します。

   <table id="table_1741878A1B284CB78D297D531DC703D6"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> 要素 </th> 
       <th colname="col2" class="entry"> 説明 </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>プロパティタイプ </p> </td> 
       <td colname="col2"> <p>実装は Web 用ですか、それともモバイル用または両方ですか？ </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>業種 </p> </td> 
       <td colname="col2"> <p>会社が収入を得る方法を指定します（製品、カスタマーサービス、リード、ブランド認知度、広告）。 </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>データ層 </p> </td> 
       <td colname="col2"> <p>（推奨）情報を保存するために使用される JavaScript 配列。Dynamic Tag Management を使用して自動セットアップを実行する場合、データ層を使用します。 </p> <p>データ層に関するブログについては、「<a href="https://blogs.adobe.com/digitalmarketing/analytics/data-layers-buzzword-best-practice/">Data Later: From Buzzword to Best Practice</a>（データ層：バズワードからベストプラクティスまで）」を参照してください。 </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>データリポジトリ（レポートスイート） </p> </td> 
       <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html">レポートスイート</a>は、通常、単一のプロパティ（サイトまたはアプリ）またはブランドに対応する、個別のデータセットです各レポートスイートには、レポートおよび指標の独自のセットがあります。 </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>タイムゾーン </p> </td> 
       <td colname="col2"> <p>ローカルタイムゾーンです（自動的に検出されます）。 </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>予想ページビュー数 </p> </td> 
       <td colname="col2"> <p>サイトが 1 日に受け取るおよそのページビュー数。 </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>基準通貨 </p> </td> 
       <td colname="col2"> <p>ビジネスに使用する通貨。 </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. 「**[!UICONTROL Next]**」をクリックします。

   システムによってレポートスイートが作成されます。

1. デプロイを開始するには、「**[!UICONTROL 次へ]**」をクリックし、次のオプションのいずれかをクリックします。

   <table id="table_71C7F7B9677346CD8D5130519D32464B"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> 要素 </th> 
       <th colname="col2" class="entry"> 説明 </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>デプロイ </p> </td> 
       <td colname="col2"> <p> Analytics にログインおよびデプロイできる <span class="keyword">Dynamic Tag Management</span> を起動します。このプロセスは、<span class="filepath">AppMeasurement.js</span> ファイルおよび ID サービス（<span class="filepath">VisitorAPI.js</span>）を自動的に実装します。 </p> <p> <p>重要：ブラウザーの新しいタブに、Dynamic Tag Management による <span class="keyword">Adobe Analytics</span> の導入手順が記載されたヘルプページが表示されます。 </p> </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>ダウンロード </p> </td> 
       <td colname="col2"> <p> <span class="filepath">INSTALL-ME &lt;report suite name&gt;.js</span> という名前のインストールファイルをダウンロードします。このオプションは、<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html">JavaScript 実装</a>を理解している経験豊富なユーザー向けです。 </p> <p> <p>重要：コードのダウンロードは、<span class="keyword">Analytics</span> のデプロイの構成要素ではありません。これは、サイトのページ上でユーザーが実行する、またはアドビのコンサルティングサービスを通じておこなう手動のデプロイです。 </p> </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. レポートを実行します。

   Analytics ツールをデプロイしたら、Reports &amp; Analytics でレポートを実行して、データがサイトに関連していることを確認します（Analytics のインターフェイスについて詳しくは、[サインインとナビゲーション](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/analytics-navigation.html)を参照してください）。

   例えば、**[!UICONTROL サイト指標]**／**[!UICONTROL リアルタイム]**&#x200B;を選択すると、即時のデータを確認できます。

   >[!NOTE]
   >
   >[!UICONTROL リアルタイム]レポートは、実行前にいくつかの設定が必要です。[リアルタイムレポートの設定](https://marketing.adobe.com/resources/help/en_US/reference/t_realtime_admin.html)を参照してください。

**リアルタイムレポートの例**

![](assets/real-time-report.png)
