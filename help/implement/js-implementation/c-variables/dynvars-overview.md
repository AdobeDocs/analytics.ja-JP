---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の導入
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
seo-title: 動的変数
solution: Analytics
subtopic: 変数
title: 動的変数
topic: 開発者と導入
uuid: 1c6db083-570e-4bc4-858d-84cf46e7bec8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 動的変数

動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。

動的変数は、同時に複数の変数から同じデータ（例えば、キャンペーントラッキングコード）を取得するために使われます。これは、様々なレポートで重要な固有の指標が提供される場合の一般的な方法です。例えば、[!UICONTROL カスタムコンバージョン]変数および[!UICONTROL カスタムトラフィック]変数で同一のサイト内部検索キーワードを取得すると、これらのキーワードにそれぞれ関連付けられている[!UICONTROL 売上高]指標と[!UICONTROL 週別訪問者数]指標を表示できます。を参照してください。

また、動的変数は様々なレポーティング状況でデータを表示する場合にも役立ちます。様々な配分設定と cookie の有効期限を設定した複数の eVar にキャンペーントラッキングコードをセットできます。これにより、ユーザーはコンバージョン指標をどのようにキャンペーンに関連付けるか、レポート時に選択できるようになります。

>[!NOTE]
>
>動的変数は、cookieと組み合わせてサポートされていません（s_ cc、s_ sq、s_ fid、s_ vi、プラグインによって設定された任意のcookie）。You can not use `D=<cookie value>`.

動的変数の大きなメリットとして、複数の変数にある長いデータ文字列を、実際にはその長い文字列を何度も受け渡すことなく習得できるという点があります。一部のブラウザーでは、HTTP GET 要求（アドビのイメージリクエストを含む）の長さの上限を設定しています。動的変数を使用することにより、いくつかの変数でデータが重複している場合、アドビのサーバーに送られる要求の長さを短縮してすべてのデータが取得されるようにします。

ページビューで生じるイメージリクエストでは、動的変数を使用して[!UICONTROL カスタムトラフィック ] の値を[!UICONTROL カスタムコンバージョン ] にコピーした場合、`v1=D=c1`1=1 と表示されます。要求で eVar1 が以前に値を受け取っていた場合、アドビのサーバーはデータプロセッシングで[!UICONTROL カスタムトラフィック 1] の値を[!UICONTROL カスタムコンバージョン 1] に動的にコピーします。その結果、[!UICONTROL カスタムトラフィック 1] を使って受け渡された元の値も[!UICONTROL カスタムコンバージョン 1] レポートに表示されます。

動的変数は、対象となる値に変数を設定し、他の変数を `D=[variable abbreviation]` ] に設定することによって受け渡されます。For abbreviations for each variable, see [Data Collection Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md). 動的変数は以下の場所からデータを取り込むことができます。

* 他のクエリ文字列変数
* HTTP ヘッダー（Cookie HTTP ヘッダーを除く）

動的変数を作成するには、変数の先頭に特殊なプレフィックスを追加します。デフォルトのプレフィックスは「D=」です。以下の 2 つの方法で動的変数を指定できます。

* デフォルトのプレフィックス D= を使用する（例： s.prop1="D=User-Agent"）
* JavaScript を使用せずに導入する場合、「D」クエリ文字列パラメーターを使用してカスタムプレフィックスを定義できます。For example, if the query-string parameter is `"&D=$"`, you can create a dynamic variable with the following command: `s.prop1="$User-Agent"` .

使用する変数の省略形は、イメージリクエストで渡される変数パラメーター名と一致する必要があります。一部の変数は、様々なケースで使用可能な複数のパラメーターを持ちます。For example, `pageName=` and `gn=` both pass the page name, but the latter is most often used in mobile and hard-coded implementations. If the image request uses `pageName=` to pass the page name, then `D=pageName` is acceptable but `D=gn` is not. If the image request uses `gn=`, then `D=gn` is acceptable, but `D=pageName` is not.

次の情報は、動的変数に適用されます。

* 動的変数は AppMeasurement コードのすべてのバージョンで利用できます。
* 動的変数では大文字と小文字が区別されます。
* 動的変数では、引用符で囲んだリテラル文字列がサポートされます。
* ルール処理や VISTA 処理などの処理の前に、動的変数の置き換えが実行されます。
* 動的変数プレフィックス「D=」は変数値の中ではなく先頭に置く必要があります。For example, use `c2='D="test7"+User-Agent'` rather than `c2='"test7"+D=User-Agent'` .

* Adobe では、すべての導入テクニックと同様に、動的変数の導入をまず開発環境で十分にテストしてから実稼動環境で実装することを強く推奨いたします。クライアントサイドのデバッグツールにはコピー後の文字列全体が表示されないので、対象となる Analytics レポートをレビューして導入が成功していることを確認してください。
* 長さの上限が異なる変数間で値をコピーする場合、コピー先の変数の上限を超える値は短縮されることに気を付けてください。例えば、[!UICONTROL カスタムトラフィック]変数には 100 文字の上限があり、[!UICONTROL カスタムコンバージョン]変数には 255 文字の上限があるとします。動的変数を使って s.eVar1 から s.prop1 に 150 文字の値をコピーする場合、この値は[!UICONTROL カスタムトラフィック]レポートで 100 文字に短縮されます。

## 動的変数の例 {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Analytics で使用可能な動的変数の例を示します。

ページビューで生じるイメージリクエストでは、動的変数を使用して[!UICONTROL カスタムトラフィック ] の値を[!UICONTROL カスタムコンバージョン ] にコピーした場合、`v1=D=c1`1=1 と表示されます。要求で eVar1 が以前に値を受け取っていた場合、アドビのサーバーはデータプロセッシングで[!UICONTROL カスタムトラフィック 1] の値を[!UICONTROL カスタムコンバージョン 1] に動的にコピーします。その結果、[!UICONTROL カスタムトラフィック 1] を使って受け渡された元の値も[!UICONTROL カスタムコンバージョン 1] レポートに表示されます。

`D=[variable]` 値は引用符で囲む必要があります。Analytics コードはこれを文字列として扱います。文字列は、URL エンコードされて Analytics に渡されます（DigitalPulse Debugger または類似のユーティリティでリクエストを表示させると確認できます）。これは正常です。Adobe's servers recognize the `D=[variable]` construction and will copy the appropriate value when they encounter this string.

>[!NOTE]
>
>リンクの追跡にイメージリクエストを使用する場合、リンクURL/名前（pev2）のようにリンクのタイプ（ダウンロード= lnk_ d、exit= lnk_ e、カスタムリンク= lnk_ o）を定義する必要があります。Links require manual implementation by inserting code within the `<a href>` tag.

>[!NOTE]
>
>動的変数は、cookieと組み合わせてサポートされていません（s_ cc、s_ sq、s_ fid、s_ vi、プラグインによって設定された任意のcookie）。You can not use `D=<cookie value>`.

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript の例 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. eVar1="D= pageName" </code>
  </td> 
   <td colname="col2"> <p>eVar1 に pageName の値をコピーします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1='D= v2+":"+ c2'&amp; amp;nbsp; </code>
  </td> 
   <td colname="col2"> <p>eVar2 と prop2 を「:」をはさんで連結した結果を prop1 にセットします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1= s. eVar1="D= g"&amp; amp;nbsp; </code>
  </td> 
   <td colname="col2"> <p>ページ URL を prop1 および eVar1 に渡します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. eVar1="D= v0" </code>
  </td> 
   <td colname="col2"> <p>eVar 1 にキャンペーンの値をコピーします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1='D= User- Agent+";-"+ Accept- Language" </code>
  </td> 
   <td colname="col2"> <p>prop1 にユーザーエージェントヘッダーと受け入れ可能言語ヘッダーを連結します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>s. prop1="D= User- Agent" </code>
  </td> 
   <td colname="col2"> <p>prop1 にユーザーエージェントをコピーします。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> イメージリクエストの例 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">/b/ss/rsid/?gn= Home&amp; D=~~&amp; c1=~~ v0/b/ss/rsid/?gn= Home&amp; D=~~&amp; c1=~~ campaign/b/ss/rsid/?gn= Home&amp; c1= D%3dv0%3dは/b/ss/rsid/?gn= Home&amp; c1=%5b%5bv0%5d%5d%5b </code>
  </td> 
   <td colname="col2"> <p>prop1 をキャンペーンに設定する 4 つの方法 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>/b/ss/rsid/?gn= Home&amp; D=~~&amp; c2=~~ x- up- subno </code>
  </td> 
   <td colname="col2"> <p> x-up-subno ヘッダーを prop2 に取り込みます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>c1= D%3DUser- Agent </code>
  </td> 
   <td colname="col2"> <p> prop1 を、HTTP ヘッダー User-Agent が入力される動的変数にします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c1= D%3D%22test%22 </code>
  </td> 
   <td colname="col2"> <p> prop1 を、文字列「test」が入力される動的変数にします。この方法は、+ 演算子を使用した連結と組み合わせるとさらに役立ちます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c1= D%3D%22US%3A%20%22%2BUser- Agent </code>
  </td> 
   <td colname="col2"> <p> prop1 を、プレフィックス「UA:」が付いた User-Agent が入力される動的変数にします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; vid= D%3DX- TM- ANTID </code>
  </td> 
   <td colname="col2"> <p> 固有ヘッダーを検索します。この例の場合は X-TM-ANTID です。 </p> </td> 
  </tr> 
 </tbody> 
</table>
