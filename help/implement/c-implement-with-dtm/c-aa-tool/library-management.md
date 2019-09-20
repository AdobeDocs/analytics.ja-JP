---
description: Dynamic Tag Management の「ライブラリ管理」設定のフィールドおよびオプションの説明です。
keywords: ライブラリ管理；ページコード；ライブラリの読み込み；adobeで管理；カスタム；コードホスト；s_codeホスト
seo-description: Dynamic Tag Management の「ライブラリ管理」設定のフィールドおよびオプションの説明です。
seo-title: ライブラリ管理
solution: Experience Cloud,Dynamic Tag Management
title: ライブラリ管理
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# ライブラリ管理

Dynamic Tag Management の「ライブラリ管理」設定のフィールドおよびオプションの説明です。

**[!UICONTROL /ツ&#x200B;*`Property`*]** ールを ![](assets/settings_gear.png) 編集 **[!UICONTROL /ラ]****[!UICONTROL イブラリ管理]**

>[!NOTE]
>
>1つのWebプロパティで複数のAdobe Analyticsツールを使用する場合、各ツールに一意のトラッカー変数名が必要です。 1 つの Web プロパティ内で使用する Adobe Analytics ツール間にオブジェクト変数名の重複があると、競合が発生します。

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>既存のページコードがある </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Adobe Analytics</span> のページコードが既にサイトに存在する場合、Dynamic Tag Management がコードをインストールするのを防ぎます。 </p> <p>この機能により、一から開始するのではなく、既存の実装に追加する形で Dynamic Tag Management を使用できます。このボックスをチェックする場合は、トラッカー変数名を適切に設定してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>&lt;<span class="term"> Page Top</span> or <span class="term"> Page Bottom</span>&gt; </p> </td> 
   <td colname="col2"> <p>ページコードを読み込むタイミングと位置を指定します。何を選択する場合にも、Analytics ツールを使用するすべてのルールで同じ設定を選択する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アドビが管理（推奨） </p> </td> 
   <td colname="col2"> <p>Dynamic Tag Management によるライブラリの管理を有効にします。 </p> <p>このオプションを選択すると、次のオプションを使用できるようになります。 </p> <p> <b>ライブラリのバージョン：</b><span class="wintitle">ライブラリのバージョン</span>メニューから最新バージョンを選択します。新しいバージョンが提供されると Dynamic Tag Management からの通知が表示されます。また、必要に応じて前のバージョンに戻ることもできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> カスタム </p> </td> 
   <td colname="col2"> <p>ライブラリコードを設定できます。 </p> <p>このオプションを選択すると、次のオプションを使用できるようになります。 </p> <p> <b>次のカスタムコードを使用してレポートスイートを設定：</b>このチェックボックスをオンにすると、Dynamic Tag Management によって、カスタムコードに含まれる  <span class="varname"> s_account</span>. この変数には、データの送信先となるレポートスイートのリストを、コンマ区切りで設定する必要があります。 </p> <p> <b>ホストするコード：</b><span class="filepath">s_code</span> をホストする方法を選択します。 </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>DTM</b>：Dynamic Tag Management 内で <span class="filepath">s_code</span> をホストできます。「<span class="uicontrol">コードを編集</span>」をクリックして、s_code（AppMeasurement）の内容を直接エディターに貼り付けます。 </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL 指定</b>：適切な <span class="filepath">s_code</span> ファイルが既に存在し、それを更新するプロセスに満足している場合、ここでそのファイルの URL を指定できます。Dynamic Tag Management は、<span class="filepath">Adobe Analytics</span> による計測のためにこの <span class="keyword">s_code</span> ファイルをロードします。 </li> 
    </ul> <p> <b>エディターを開く：コア </b>のAppMeasurement <a href="../../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658" format="dita" scope="local"> コードを挿入できます</a>。 This code is populated automatically when using the automatic configuration method described in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8" format="dita" scope="local"> Adobe Analytics Settings</a>. </p> <p> <b>トラッカー変数名：2つ </b>のAdobe Analyticsインスタンスを並行して(1つはDynamic Tag Management内で、もう1つはネイティブで <span class="keyword"> )実行する場合は、メインのsオブジェクトの名前を変更で</span> きます <span class="term"></span> 。 オブジェクト名を変更すると名前の競合を避けることができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

