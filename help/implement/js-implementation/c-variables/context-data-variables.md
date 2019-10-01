---
description: コンテキストデータ変数を使用すると、処理ルールで読み取れる各ページ上にカスタム変数を定義できます。
keywords: Analytics Implementation;contextdata;s.contextdata
seo-description: コンテキストデータ変数を使用すると、処理ルールで読み取れる各ページ上にカスタム変数を定義できます。
seo-title: コンテキストデータ変数
solution: Analytics
subtopic: 変数
title: コンテキストデータ変数
topic: 開発者と実装
uuid: 4b215803-99d4-46f2-b3c1-e7855898764
translation-type: tm+mt
source-git-commit: 959e4963eafe6e32a55b2ce9659fe43ea8086527

---


# コンテキストデータ変数

コンテキストデータ変数を使用すると、処理ルールで読み取れる各ページ上にカスタム変数を定義できます。

prop と eVar にコードで明示的に値を割り当てる代わりに、処理ルールを使用して、マッピングされるコンテキストデータ変数にデータを送信できます。処理ルールは、受信したデータに変更を加えるための強力なグラフィカルインターフェイスです。コンテキストデータで送信された値に基づいて、イベントを設定し、値を eVar および prop にコピーし、追加の条件文を実行できます。

>[!NOTE]
>
>コンテキストデータ変数では、大文字と小文字が区別されません。 例えば、以下の 2 つの変数は実際には同一です。
>```
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>```
>と
>```
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```

コンテキストデータを使用すると、レポートスイート設定を変更するためにコードを更新する必要性が減ります。

例えば、以下の  *`s.contextData`* variable:

```
s.contextData['myco.rsid'] = 'value'
```

処理ルールでは、`myco.rsid` コンテキストデータ変数を確認する条件を追加できます。この変数がある場合は、それを prop または eVar にコピーするアクションを追加できます。

また、コンテキストデータ変数を処理ルールインターフェイスで直接定義して、値を一時的に保存したり、レポートスイートで使用される既知のコンテキストデータ変数から値を収集したりすることもできます。例えば、2 つの値を入れ替える必要がある場合は、コンテキストデータ変数を作成して入れ替えの間に値を保存できます。

処理ルールはデータが収集されるときにのみ適用されるので、コンテキストデータの送信を開始する前に、処理ルールを設定することが重要です。ヒットが処理されるときに処理ルールで読み込まれなかったコンテキストデータ値は、破棄されます。

## ルール {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>ルール </p> </th> 
   <th colname="col2" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>サポートされる名前と文字 </p> </td> 
   <td colname="col2"> <p>コンテキストデータ変数の名前には、英数字、アンダースコアおよびドットのみを使用できます。その他の文字はすべて削除されます。コンテキストデータ変数は、数字ではなく名前で参照されます。 </p> <p>例えば、コンテキストデータ変数 <code>login_page-home</code> は自動的に <code>login_pagehome</code> になります。<code>login_page-home</code> 変数に送信されるすべてのデータは、<code>login_pagehome</code> で割り当てられます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名前空間 </p> </td> 
   <td colname="col2"> <p>変数の先頭には会社名やサイト名などの値を付けて、レポートスイート全体で名前が一意になるようにすることをお勧めします。 </p> <p>コンテキストデータ変数は、他の JavaScript 変数に類似した名前を付けることができます。namespace <code>a.*</code> の使用はアドビ製品のコンテキスト変数名で予約されているので注意してください。例えば、AppMeasurement for iOS ライブラリでは、<code>a.InstallEvent</code> を使用してアプリケーションのインストールを測定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL Limits for Internet Explorer </p> </td> 
   <td colname="col2"> <p>Internet Explorer 6 および 7 で、URL が 2,000 バイト以下に切り捨てられるという古い URL の制限が発生する場合があります。<span class="keyword">DigitalPulse</span> Debugger を使用して URL 文字列のサイズを決定できます。 </p> <p>AppMeasurement の最近のアップデート（2014 年 9 月）では、Internet Explorer 8 以上で HTTP POST が使用され、切り捨ての問題が解決されています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サポートされる AppMeasurement バージョン </p> </td> 
   <td colname="col2"> <p>コンテキストデータ変数を使用するには、H23 コード以降が必要です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## リンクトラッキングでのコンテキストデータの送信 {#section_35EBE5D1CF29427598BD4B2165CE64FC}

`ContextData` 内で、`s.linkTrackVars` の後に、含める変数の名前を指定します。

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## 例 {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possible ways to replace implementation of the  variable, assuming that processing rules are set up correctly for each:*`s.pageName`*

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

コンテキストデータ変数の他の導入例を示します。

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

例については、Analytics リファレンスの[コンテキストデータ変数の eVar へのコピー](https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_copy_context_data.html)を参照してください。
