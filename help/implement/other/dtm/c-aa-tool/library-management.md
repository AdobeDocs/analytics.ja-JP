---
description: Dynamic Tag Management の「ライブラリ管理」設定のフィールドおよびオプションの説明です。
keywords: library management;page code;load library at;managed by adobe;custom;code hosted;s_code hosted
solution: Experience Cloud,Dynamic Tag Management
title: ライブラリ管理
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# ライブラリ管理

Dynamic Tag Management の「ライブラリ管理」設定のフィールドおよびオプションの説明です。

**[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Library Management]**

>[!NOTE]1 つの Web プロパティで複数の Adobe Analytics ツールを使用する場合は、ツールごとに異なる名前のトラッカー変数を使用する必要があります。1つのWebプロパティ内でAdobe Analyticsツール間でオブジェクト変数名の重複が発生すると、競合が発生します。

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ページコードが既に存在します </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Adobe Analytics</span> のページコードが既にサイトに存在する場合、Dynamic Tag Management がコードをインストールするのを防ぎます。 </p> <p>この機能を使用すると、一から開始するのではなく、Dynamic Tag Managementを使用して既存の実装を追加できます。 このボックスをチェックする場合は、トラッカー変数名を適切に設定してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>&lt;Page Top<span class="term"> or</span> Page Bottom <span class="term"></span>&gt;にライブラリを読み込む </p> </td> 
   <td colname="col2"> <p>ページコードを読み込む場所とタイミングを指定します。 選択内容にかかわらず、Analyticsツールを使用するルールはすべて同じ設定を持つ必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アドビが管理（推奨） </p> </td> 
   <td colname="col2"> <p>Dynamic Tag Managementを有効にして、ライブラリを管理します。 </p> <p>このオプションを選択すると、次のオプションを使用できるようになります。 </p> <p> <b>ライブラリのバージョン：</b><span class="wintitle">ライブラリのバージョン</span>メニューから最新バージョンを選択します。新しいバージョンが利用可能になると、Dynamic Tag Managementから通知されます。 必要に応じて、以前のバージョンに戻すことができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> カスタム </p> </td> 
   <td colname="col2"> <p>ライブラリコードを設定できます。 </p> <p>このオプションを選択すると、次のオプションが使用可能になります。 </p> <p> <b>次のカスタムコードを使用してレポートスイートを設定：</b>このチェックボックスをオンにすると、Dynamic Tag Management によって、カスタムコードに含まれる      <span class="varname"> s_account</span> 変数を探します。この変数には、データの送信先となるレポートスイートのリストを、コンマ区切りで設定する必要があります。 </p> <p> <b>ホストするコード：</b><span class="filepath">s_code</span> をホストする方法を選択します。 </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>DTM</b>：Dynamic Tag Management 内で <span class="filepath">s_code</span> をホストできます。「<span class="uicontrol">コードを編集</span>」をクリックして、ファイルを直接エディターに貼り付けます。 </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL 指定</b>：適切な <span class="filepath">s_code</span> ファイルが既に存在し、それを更新するプロセスに満足している場合、ここでそのファイルの URL を指定できます。Dynamic Tag Management は、<span class="filepath">Adobe Analytics</span> による計測のためにこの <span class="keyword">s_code</span> ファイルをロードします。 </li> 
    </ul> <p> <b>エディターを開く：</b><a href="/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md"  >コア AppMeasurement コードを挿入</a>できます。「<a href="/help/implement/other/dtm/c-aa-tool/analytics-dtm.md"  >Adobe Analytics 設定</a>」で説明した自動設定メソッドを使用すると、このコードは自動生成されます。 </p> <p> <b>トラッカー変数名：</b>2 つの <span class="keyword">Adobe Analytics</span> インスタンスを並行して（1 つは Dynamic Tag Management で、もう 1 つはネイティブで）実行する場合に、メインの <span class="term">s</span> オブジェクトの名前を変更できます。オブジェクト名を変更すると名前の競合を避けることができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

