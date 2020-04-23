---
description: リンクレポートは、現在のページで見つかったリンクを報告します。 そのページに対して収集されたすべてのリンクに関するレポートは作成されません。
title: リンクレポート
topic: Activity map
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
translation-type: tm+mt
source-git-commit: 6b27755178d156b1eaf159640d466bd84659983d

---


# リンクレポート

リンクレポートは、現在のページで見つかったリンクを報告します。 そのページに対して収集されたすべてのリンクに関するレポートは作成されません。

ページ上のリンクレポートは、オファー形式のリンクの表示を表形式で表示します。 リンククリック数（または他の指標）を1つの表示でランク付けして表示したい場合があります。 これにより、あるリンクと別のリンクを比較しやすくなります。 ページ上のすべてのリンクのランクリスト（リンクID別）、クリック情報（#と%）およびページ内の領域を含む、ページ上のリンクレポートを作成します。 [ページ内のリンク]レポートボタン([アクティビティマップ]ツールバー)をクリックします。

The **[!UICONTROL Links On Page]** report opens below the browser frame in the Activity Map dashboard.

## 標準モード {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

標準モードでは、「ページ上のリンク」レポートに、1日から複数日に及ぶリンクデータが、全日付範囲にわたって集計して表示されます。 各リンクに関して、次の情報が表示されます。

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 列 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ランク </td> 
   <td colname="col2"> ページ内のランク。 標準モードでは、どの列をクリックしても、ランクの値は同じままです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リンク ID </td> 
   <td colname="col2">The link's primary ID (for more information on how primary ID is defined by the <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">New Link Tracking Methodology</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> クリック数 </td> 
   <td colname="col2"> 指定したリンクの生のクリック数と、ページ上の合計クリック数に対する割合。 ユーザーがツールバーで別の指標を選択した場合、リンクレポートはその指標ではなくその指標をレポートします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 領域 </td> 
   <td colname="col2"> ページ内でリンクが配置されている領域を表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 視認性 </td> 
   <td colname="col2">リンクの表示ステータスに関連します。 次の2つの値を指定できます。 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>非表示</b>:リンクは現在ページにありますが、エンドユーザーには表示されません（親メニューの上にカーソルを置いた場合にのみ表示されるナビゲーションメニューのサブメニューなど）。 </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>表示</b>:リンクは現在、ページに表示されています。 ただし、次の場所に表示される場合があります。ページを表示するには、ページをスクロールする必要があります。 </li>
    </ul><p>注意：「非表示」に設定されているリンクのオーバーレイは表示されません。 </p></td> 
  </tr> 
 </tbody> 
</table>

**データをフィルター**

When you want to zero in on a specific link, you can search for a related term in the **[!UICONTROL Filter Data]** field. 検索に一致するリンクのみがオーバーレイを持ちます。 フィルターを適用しない場合、「 [アクティビティマップ設定](/help/analyze/activity-map/activitymap-overlay-settings.md) 」で指定したオーバーレイが表示されます。

## ライブモード {#section_AC1967217B5A4532ACB01D33636F6770}

ライブモードでは、ページ上のリンクレポートに、数分間にわたるトレンドデータが表示されます。

![](assets/links_on_page.png)

<table id="table_61D1FB0F02894055A1AB394DE4FE4742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 列 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ランク </td> 
   <td colname="col2"> ページ内のランク。 グラデーションまたはバブルのオーバーレイの場合、どの列をクリックしても、ランクの値は同じままです。 勝者/敗者のオーバーレイの場合、ランク値は、最も多く得た/失われたリンクに基づいて変化します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リンク ID </td> 
   <td colname="col2">リンクのプライマリID。 For more information on how the primary ID is defined by the New <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> Link Tracking Methodology</a>. </td>
  </tr> 
  <tr> 
   <td colname="col1"> リンククリック数 </td> 
   <td colname="col2"> 選択した期間の合計クリック数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % 前回比 </td> 
   <td colname="col2"> 現在の期間のリンク指標と前の期間のリンク指標の変化の割合。 負の変化率は赤、正の変化率は緑で表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トレンド </td> 
   <td colname="col2"> すべての収集期間の折れ線グラフ。 現在選択されている期間は、緑のマーカーで示されます。 現在カーソルを合わせた期間は赤いマーカーで示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 領域 </td> 
   <td colname="col2"> ページ内でリンクが配置されている領域を表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 視認性 </td> 
   <td colname="col2">リンクの表示ステータスに関連します。 次の2つの値を指定できます。 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">非表示：リンクは現在ページ内にありますが、表示されていません（ページの読み込み後に表示されるリンクなど）。 </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">表示：リンクは現在、ページに表示されています。 ただし、次の場所に表示される場合があります。ページをスクロールして表示する必要があります。 </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 並べ替えとフィルター {#section_4B8E8233C21247CAA70DAEC2156548AD}

特定のページ領域（左パネルなど）の結果のみを分析して、Webページの特定の領域のコンテンツの編成方法を決定する必要がある場合があります。

この目的で、ページ上のリンクレポートのリンクの並べ替えとフィルタリング機能を作成しました。 フィルターはフィルターフィールドから使用でき、検索語句は「リンクID」列と「リンク領域」列に適用されます。 並べ替えは、コールオン（ランク、リンクID、クリック数、経時的な変化、地域、表示）をクリックすることで実行でき、昇順と降順の両方で行うことができます。 ページ上のリンクレポートからリンクがフィルターで除外されると、オーバーレイがWebサイトに表示されなくなります。
