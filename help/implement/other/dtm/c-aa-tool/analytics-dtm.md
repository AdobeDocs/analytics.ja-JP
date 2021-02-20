---
description: Dynamic Tag Management を使用して Adobe Analytics をデプロイするには、Adobe Analytics ツールを作成し、自動または手動でページコードを設定します。ほとんどの場合は、自動的な導入方法をお勧めします。
keywords: Analytics の実装, 実装方法, dynamic tag management, dtm, analytics ツール, プロパティ, ツールタイプ, ツール名, 設定方法, analytics premium, evar, イベント
title: Adobe Analytics ツールの追加
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 100%

---


# Adobe Analytics ツールの追加

Dynamic Tag Management を使用して Adobe Analytics をデプロイするには、Adobe Analytics ツールを作成し、自動または手動でページコードを設定します。ほとんどの場合は、自動的な導入方法をお勧めします。

>[!NOTE]
>
> 訪問者のトラッキング機能を強化するには、[ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を有効にすることを強くお勧めします。

## Adobe Analytics ツールの追加 {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. **[!UICONTROL *`Web Property Name`*]**／**[!UICONTROL &#x200B;概要&#x200B;]**／**[!UICONTROL &#x200B;ツールの追加&#x200B;]**／**[!UICONTROL  Adobe Analytics ]** をクリックします。

   ![](assets/dtm-add-analytics-tool.png)

1. 以下のフィールドを設定します。

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ツールタイプ </p> </td> 
   <td colname="col2">「<span class="keyword">Adobe Analytics</span>」などのツールの種類。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ツール名 </p> </td> 
   <td colname="col2">このツールのわかりやすい名前。この名前は、「<span class="wintitle">インストールされているツール</span>」の「<span class="wintitle">概要</span>」タブに表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>設定方法 </p> </td> 
   <td colname="col2"> <p> <b>自動</b>（推奨）：Dynamic Tag Management を使用して設定を管理します。この方法では、<span class="keyword">Experience Cloud</span> ログインまたは Web サービスの ID を使用して、<span class="keyword">Adobe Analytics</span> レポートスイートの自動的な同期を有効にし、AppMeasurement コードを管理できます。 </p> <p>アカウントが接続されると、<span class="keyword">Adobe Analytics</span> レポートスイート ID と名前が取得され、ツール設定インターフェイスに入力されます。したがってユーザーのミスが発生しにくく、ツールのデプロイメントを迅速に実行できます。 </p> <p> <p>注意：<span class="wintitle">Adobe Analytics Premium</span> をお使いの場合は、「<span class="keyword">自動</span>」オプションを選択する必要があります。 </p> </p> <p>自動設定に特有のフィールドに設定を入力します。 </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>：（デフォルト）<span class="keyword">Experience Cloud</span> のシングルサインオンを使用します。お使いの Experience Cloud ID とパスワードを入力してください。 </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Web サービス</b>：Web サービスのユーザー名と共有暗号鍵を指定します。 </p> <p>共有暗号鍵資格情報は、<span class="uicontrol">管理</span>／<span class="uicontrol">カンパニー設定</span>／<a href="https://docs.adobe.com/content/help/ja-JP/analytics/admin/company-settings/web-services-admin.html">Web サービス</a>にあります。 </p> <p>Web サービス資格情報の取得については、開発者向けの<a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api">企業 API への Web サービスアクセスの取得</a>を参照してください。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>手動</b>：AppMeasurement コードを手作業で管理します。<span class="keyword">Analytics</span> の <span class="keyword">AppMeasurement</span> コードは、<span class="ignoretag"><span class="uicontrol">管理ツール</span>／<span class="uicontrol">コードマネージャー</span></span>からダウンロードできます。 </p> <p>「<a href="https://docs.adobe.com/content/help/ja-JP/analytics/implementation/js/migrate-from-hcode.html">JavaScript（新規）</a>」をクリックして、コードをローカル環境にコピーし、「<a href="/help/implement/other/dtm/c-aa-tool/library-management.md">ライブラリ管理</a>」の「<span class="wintitle">コードを編集</span>」フィールドに貼り付けます。 </p> <p>手動設定に特有のフィールドに設定を入力します。 </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>実稼動アカウント ID</b>：（必須）データ収集用の実稼動アカウント。Analytics の場合はレポートスイート ID になります。Dynamic Tag Management は、実稼動およびステージング環境に適したアカウントを自動的にインストールします。 </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ステージングアカウント ID</b>：（必須）開発環境またはテスト環境で使用するアカウント。Analytics の場合はレポートスイート ID になります。ステージングアカウントには、実稼動用データとは別個のテストデータが保持されます。 </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>トラッキングサーバー</b>：使用するトラッキングサーバーの情報を指定します。 </p> <p>「<span class="wintitle">トラッキングサーバー</span>」および「<span class="wintitle">SSL トラッキングサーバー</span>」変数は、画像リクエストや Cookie の書き込み先ドメインを指定するファーストパーティ Cookie 実装のために使用されます。詳しくは、<a href="https://helpx.adobe.com/jp/analytics/kb/determining-data-center.html">trackingServer および trackingServerSecure 変数の適切な設定</a>を参照してください。 </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>SSL トラッキングサーバー</b>：使用する SSL トラッキングサーバーの情報を指定します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. 「**[!UICONTROL ツールを作成]**」をクリックしてツールを作成し、編集用に表示します。

   ツールは、「[!UICONTROL インストールされているツール]」の「[!UICONTROL 概要]」タブに表示されます。

1. （場合によって手順が異なる）下のリンク先に記載された手順に従って、必要に応じたツール設定作業を進めます（[!UICONTROL 一般]、[!UICONTROL ライブラリ管理]、[!UICONTROL グローバル変数]、[!UICONTROL ページビューおよびコンテンツ]、[!UICONTROL リンクトラッキング]、[!UICONTROL リファラーおよびキャンペーン]、[!UICONTROL Cookie]、[!UICONTROL ページコードをカスタマイズ]）。

[Adobe Analytics ツールに関するよくある質問](/help/implement/faq.md)を参照してください。

## 既存の Adobe Analytics ツールの編集 {#section_148B16AF429B4949B06238D90635B726}

既存の Adobe Analytics ツールは、編集することで設定を変更できます。

1. 「 [!UICONTROL 概要]」タブで、インストールされているツールの横にある ![](assets/settings_gear.png) アイコンをクリックします。
1. 必要に応じてフィールドを編集します。

   上で説明した Analytics ツール作成時に使用できる要素との差分のみを次の表に示します。両方の表に記載したとおり、ページ内の要素はすべて変更を加えることができます。

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>自動設定を有効にする </p> </td> 
   <td colname="col2"> <p>注：この設定を有効にすると、手動で設定した実装が、「<span class="term">設定メソッド</span>」で説明した自動設定メソッドに代わります。 </p> <p>このオプションを選択すると、Dynamic Tag Management によって <span class="keyword">Adobe Analytics</span> アカウントの設定が自動取得されます。 </p> <p>利用可能な最新の AppMeasurement コードが使用され、新しいバージョンが提供されるとアップグレード通知が表示されて選択可能になります。互換性などの必要に応じて、古い AppMeasurement バージョンに戻すこともできます。最大で 5 つの古いバージョンが表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資格情報を更新 </p> </td> 
   <td colname="col2"> <p>ユーザーに関連付けられたレポートスイートを更新する目的などのために、API を最新の状態に更新します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. （場合によって手順が異なる）下のリンク先に記載された手順に従って、必要に応じたツール設定作業を進めます（[!UICONTROL 一般]、[!UICONTROL ライブラリ管理]、[!UICONTROL グローバル変数]、[!UICONTROL ページビューおよびコンテンツ]、[!UICONTROL リンクトラッキング]、[!UICONTROL リファラーおよびキャンペーン]、[!UICONTROL Cookie]、[!UICONTROL ページコードをカスタマイズ]）。
1. 「**[!UICONTROL 変更を保存]**」をクリックします。
