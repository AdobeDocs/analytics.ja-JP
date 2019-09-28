---
description: 管理におけるレポートスイートの一般的なアカウント設定のフィールドの説明。
seo-description: 管理におけるレポートスイートの一般的なアカウント設定のフィールドの説明。
seo-title: 一般的なアカウント設定
solution: Analytics
title: 一般的なアカウント設定
topic: 管理ツール
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: 3c5cc9275c9978caf57e4e29704e23405ac24b65

---


# 一般的なアカウント設定

管理におけるレポートスイートの一般的なアカウント設定のフィールドの説明。

**[!UICONTROL Analytics]** /管理者 **[!UICONTROL /]** レポート **[!UICONTROL Suites]** /設定の編集/一般 **[!UICONTROL Settings/一般General]** Account ******[!UICONTROL Settings]**

これらの設定には、名前やタイムゾーンなど、基本的なレポートスイート機能の編集オプションが含まれます。

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> サイトのタイトル</span> </td> 
   <td colname="col2"> <p>サイトを識別します。各レポートスイートに一意のサイトタイトルを付けます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Base URL</span> </td> 
   <td colname="col2"> <p>レポートスイートのメインの Web サイトを指定します。ベース URL はリファラーのフィルタリングには影響しません。代わりに、<a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local">内部 URL</a> を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> タイムゾーン</span> </td> 
   <td colname="col2"> <p>レポートデータに関連付けられている日付と時刻を決定します。 </p> <p>使用中のレポートスイートのタイムゾーンを変更すると、レポートデータにスパイクまたはギャップが発生します。影響を最小にするため、タイムゾーンをピークでない時間帯に変更し、データの混乱を避けることをお勧めします。 </p> <p>例えば、レポートスイートのタイムゾーンを午後 3 時に米国中部標準時から太平洋標準時に変更すると、そのレポートスイートの現在の時間は午後 1 時になります。午後 1 時のデータを既に収集しているので、レポートには午後 1 時から 3 時の間のトラフィックスパイクが表示されます。 </p> <p>または、レポートスイートのタイムゾーンを午後 3 時に米国中部標準時から東部標準時に変更すると、そのレポートスイートの現在の時間は午後 4 時になります。レポートには、時間を変更した日の午後 3 時から午後 4 時の間のデータが表示されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> コンバージョンレベル</span> </td> 
   <td colname="col2"> <p> eVar やキャンペーンなどの e コマース変数を有効または無効にします。サイトに買い物かごがない場合は、「<span class="uicontrol">有効、買い物かごなし</span>」オプションを使用すると、すべての買い物かごレポートが非表示になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> デフォルトのページ</span> </td> 
   <td colname="col2"> <p> <span class="wintitle">最頻訪問ページレポート</span>にページ名ではなく URL がある場合に、この設定によって同じ ページが複数の URL で表されることを防止できます。For example, the URLs <span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove default filenames so that these two URLs would both show up as <span class="filepath"> https://mysite.com</span>. </p> <p>空白のままにすると、URL から <span class="filepath">index.htm</span>、 <span class="filepath">index.html</span>、 <span class="filepath">index.cgi</span>、 <span class="filepath">index.asp</span>、 <span class="filepath">default.htm</span>、 <span class="filepath">default.html</span>、 <span class="filepath">default.cgi</span>、 <span class="filepath">default.asp</span>、 <span class="filepath">home.htm</span>、 <span class="filepath">home.html</span>、 <span class="filepath">home.cgi</span>、 <span class="filepath">home.asp</span> といったファイル名が削除されます。 </p> <p>ファイル名の削除を完全に無効にするには、URL に決して存在しない値を入力してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle">IP アドレスの最後のオクテットを 0 に置き換えます</span> </td> 
   <td colname="col2"> <p>最後のオクテットの削除が、IP フィルタリングの前におこなわれます。最後のオクテットが 0 に置換されるので、末尾が 0 の IP アドレスに一致するように IP 除外ルールを更新します。「* に一致」は、 0 にも一致します。 </p> <p>このオプションを選択すると、IP アドレスが処理される前に変更されます。例えば、IP アドレス 134.123.567.780 は 134.123.567.0 に変更されます。地理特性データは、変更前の IP アドレスを使用した場合と正確には一致しません。Specifically, city accuracy is going to be more affected than country or region accuracy. 変更前の IP アドレスは、ボットルールと VISTA ルールのどちらでも使用できないので、これらのルールは共に影響を受けます。また、マーケティングチャネルルールやレポートスイート処理ルールなどの IP ベースの処理ルールも、この設定の影響を受けます。 </p> <p>注意： 2019 年 1 月以降、ロンドンデータセンターで作成される新しいレポートスイートでは、この設定がデフォルトで有効になりますが、これは、そのレポートスイートの設定が、Admin Console に一覧表示されるテンプレートからコピーされた場合に限ります。他のレポートスイートから設定をコピーしたレポートスイートでは、すべての設定が、選択したレポートスイートから継承されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> IP Obfuscation（IP の不明化）</span> </td> 
   <td colname="col2"> <p>IP アドレスを認識不可能な文字列に変更して、アドビのデータストアから削除します。IP の不明化を有効にすると、元の IP アドレスは永久に失われます。 </p> <p>注意：Data Warehouse を含め、Analytics のどこでも、IP アドレスが不明化されます。ただし、Target の IP 設定は別に制御されているので、この設定が Target に影響することはありません。 </p> <p>IP の不明化を有効にすると、IP アドレスが不明化される前に IP の除外がおこなわれるので、IP の不明化を有効にする際に、お客様は何も変更する必要はありません。 </p> <p>「<span class="uicontrol">無効</span>」をチェックすると、データの IP アドレスはそのまま変更されません。 </p> <p>「<span class="uicontrol">IP アドレスを不明化</span>」をチェックすると、IP がハッシュ値（234abc6493872038 など）に変更されます。 </p> <p>「<span class="uicontrol">IP アドレスを削除</span>」をチェックすると、地域ルックアップ後に IP アドレスがデータ内で x.x.x.x に置き換えられます。 </p> <p>注意：この設定では、カスタムボットルールまたは <a href="../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> IP除外の変更</a> が必要になる場合があります<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"></a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> トランザクション ID ストレージ</span> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html" format="https" scope="external">トランザクション ID</a> データソースを使用できるようにします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Ad Hoc Analysis をアクティブ化</span> </td> 
   <td colname="col2"> <p>問題になっているレポートスイートが Ad Hoc Analysis で利用可能なレポートスイートとして表示されているかどうかを示します。この設定を使用して、どのレポートスイートが Ad Hoc Analysis のオプションとして表示されるかを制限します。例えば、開発および QA のレポートスイートの Ad Hoc Analysis を無効にできます。 </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> Data Warehouse を有効化</span> </td> 
   <td colname="col2"> <p><span class="uicontrol">ツール</span>／<span class="uicontrol">Data Warehouse</span> から Data Warehouse UI を有効にします。 </p> </td> 
  </tr> 
 </tbody> 
</table>

