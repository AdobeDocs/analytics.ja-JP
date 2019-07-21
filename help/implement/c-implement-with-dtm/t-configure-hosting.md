---
description: Dynamic Tag Management は、利用可能なホスティングオプションを 1 つ以上利用して実装できます。
keywords: Analyticsの導入;導入方法、Dynamic Tag Management;dtm;ホスティング;ホスティングオプション、Akamai;自己ホスト;自己ホスト;ftp Delivery;FTPホスティング;ライブラリのダウンロード
seo-description: Dynamic Tag Management は、利用可能なホスティングオプションを 1 つ以上利用して実装できます。
seo-title: ホスティングオプションの設定
solution: Analytics
title: ホスティングオプションの設定
topic: 開発者と導入
uuid: 04268f2d- e76f-4fe4-8fcc- f0db3a016502
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# ホスティングオプションの設定

You can deploy [!UICONTROL Dynamic Tag Management] using one or more of the available hosting options.

[!UICONTROL Dynamic Tag Management には、タグ管理に最低限必要な JavaScript ファイルをホストするための多くの配信オプションが用意されています。]

ホスティングについて詳しくは、Dynamic Tag Management 製品ドキュメントの[埋め込みコードとホスティングオプション](https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html)を参照してください。

「埋め込み」タブで、ホスティングオプションを選択します。

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ホスティングオプション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> 実装 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> 実装が最もシンプルなホスティングオプションです。 </p> <p>グローバルな分散配信ネットワークです。 </p> <p>サードパーティインフラストラクチャに対する依存関係（DNS ルックアップ、Akamai の可用性）が発生します。 </p> <p>詳しくは、Dynamic Tag Management 製品ドキュメントの <a href="https://marketing.adobe.com/resources/help/en_US/dtm/akamai.html" format="html" scope="external">Akamai</a> を参照してください。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Dynamic Tag Management が自動で、カスタム JavaScript ライブラリを生成します。 </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Dynamic Tag Management が、Akamai にカスタム JavaScript ライブラリをエクスポートします。 </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">対象の Web サイトは、Akamai がホストする Dynamic Tag Management ライブラリをページレベルで直接参照します。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自己ホスト型：FTP 配信 </td> 
   <td colname="col2"> <p><span class="term"> プッシュ</span> アプローチ。Dynamic Tag Managementは、FTPプロトコルを介してWebコンテンツサーバーホストに直接カスタムJavaScriptライブラリをエクスポートします。 </p> <p>このソリューションでは、カスタム Dynamic Tag Management ライブラリに対して変更を発行するために、Web コンテンツサーバー上の FTP サーバーおよび資格情報を使用する必要があります。 </p> <p>詳しくは、Dynamic Tag Management 製品ドキュメントの <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_ftp.html" format="html" scope="external">FTP</a> を参照してください。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Dynamic Tag Management が自動で、カスタム JavaScript ライブラリを生成します。 </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Dynamic Tag Management が、FTP を使用してホストサーバーにカスタム JavaScript ライブラリをエクスポートします。 </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">対象の Web サイトは、カスタムの Dynamic Tag Management ライブラリをローカルで参照します。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自己ホスト型：ライブラリのダウンロード </td> 
   <td colname="col2"> <p><span class="term"> プル</span> アプローチ。アプリケーションはカスタムJavaScriptライブラリをエクスポート <!-- to Amazon S3-->します。ライブラリは、ホストされたサーバーサイドのプロセスからアクセスできます。 </p> <p>さらに、ライブラリは、Dynamic Tag Management インターフェイスから直接 Web ダウンロードして使用できます。 </p> <p>このソリューションでは、Dynamic Tag Management ライブラリを手動で取得して発行するか、Akamai から Web コンテンツサーバーにライブラリを自動的に転送するプログラムを開発する必要があります。 </p> <p>このアプローチは、セットアップに最も多くの時間がかかりますが、最も安全で柔軟なオプションでもあります。 </p> <p>最新バージョンのライブラリファイルが参照されているかどうかを確認するには、コマンドを使用します。 </p> <p>詳しくは、Dynamic Tag Management 製品ドキュメントの<a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_download.html" format="html" scope="external">ライブラリのダウンロード</a>を参照してください。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Dynamic Tag Management が自動で、カスタム JavaScript ライブラリを生成します。 </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Dynamic Tag Management が、Akamai にカスタム JavaScript ライブラリをエクスポートします。 </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">カスタム Dynamic Tag Management ライブラリを手動またはプログラムで Web コンテンツサーバーに転送します。 </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">対象の Web サイトは、カスタムの Dynamic Tag Management ライブラリをローカルで参照します。 </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

複数のホスティングオプションを使用できます。例えば、Akamai を使用してステージファイルをホストする一方で、実稼動サイトを自己ホストできます。ホスティングタイプごとに独自の埋め込みコードがあり、1 つのページに追加できる埋め込みコードは 1 つだけです。
