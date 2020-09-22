---
description: Dynamic Tag Management の「ライブラリ管理」設定のフィールドおよびオプションの説明です。
keywords: library management;page code;load library at;managed by adobe;custom;code hosted;s_code hosted
solution: Experience Cloud
title: ライブラリ管理
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---


# ライブラリ管理

Dynamic Tag Management の「ライブラリ管理」設定のフィールドおよびオプションの説明です。

**[!UICONTROL *`Property`*]**／![](assets/settings_gear.png)**[!UICONTROL &#x200B;ツールを編集&#x200B;]**／**[!UICONTROL &#x200B;ライブラリ管理&#x200B;]**

>[!NOTE]
>
>1 つの Web プロパティで複数の Adobe Analytics ツールを使用する場合は、ツールごとに異なる名前のトラッカー変数を使用する必要があります。1 つの Web プロパティ内で使用する Adobe Analytics ツール間にオブジェクト変数名の重複があると、競合が発生します。

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
   <td colname="col1"> <p>&lt;<span class="term">ページ上部</span>または<span class="term">ページ下部</span>&gt; でライブラリを読み込む </p> </td> 
   <td colname="col2"> <p>ページコードを読み込むタイミングと位置を指定します。何を選択する場合にも、Analytics ツールを使用するすべてのルールで同じ設定を選択する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アドビが管理（推奨） </p> </td> 
   <td colname="col2"> <p>Dynamic Tag Management によるライブラリの管理を有効にします。 </p> <p>このオプションを選択すると、次のオプションを使用できるようになります。 </p> <p> <b>ライブラリのバージョン：</b><span class="wintitle">ライブラリのバージョン</span>メニューから最新バージョンを選択します。新しいバージョンが提供されると Dynamic Tag Management からの通知が表示されます。また、必要に応じて前のバージョンに戻ることもできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> カスタム </p> </td> 
   <td colname="col2"> <p>ライブラリコードを設定できます。 </p> <p>このオプションを選択すると、次のオプションを使用できるようになります。 </p> <p> <b>次のカスタムコードを使用してレポートスイートを設定：</b>このチェックボックスをオンにすると、Dynamic Tag Management によって、カスタムコードに含まれる         <span class="varname"> s_account</span> 変数を探します。この変数には、データの送信先となるレポートスイートのリストを、コンマ区切りで設定する必要があります。 </p> <p> <b>ホストするコード：</b><span class="filepath">s_code</span> をホストする方法を選択します。 </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>DTM</b>：Dynamic Tag Management 内で <span class="filepath">s_code</span> をホストできます。「<span class="uicontrol">コードを編集</span>」をクリックして、ファイルを直接エディターに貼り付けます。 </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL 指定</b>：適切な <span class="filepath">s_code</span> ファイルが既に存在し、それを更新するプロセスに満足している場合、ここでそのファイルの URL を指定できます。Dynamic Tag Management は、<span class="filepath">Adobe Analytics</span> による計測のためにこの <span class="keyword">s_code</span> ファイルをロードします。 </li> 
    </ul> <p> <b>エディターを開く：</b> <a href="/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md"  >コア AppMeasurement コードを挿入</a>できます。「<a href="/help/implement/other/dtm/c-aa-tool/analytics-dtm.md"  >Adobe Analytics 設定</a>」で説明した自動設定メソッドを使用すると、このコードは自動生成されます。 </p> <p> <b>トラッカー変数名：</b>2 つの <span class="keyword">Adobe Analytics</span> インスタンスを並行して（1 つは Dynamic Tag Management で、もう 1 つはネイティブで）実行する場合に、メインの <span class="term">s</span> オブジェクトの名前を変更できます。オブジェクト名を変更すると名前の競合を避けることができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

