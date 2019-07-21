---
description: マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。
seo-description: マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。
seo-title: マーケティングチャネルの管理
solution: Analytics
subtopic: マーケティングチャネル
title: マーケティングチャネルの管理
topic: Reports and Analytics
uuid: 9d367bb6- a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# マーケティングチャネルの管理

マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。

## Manage marketing channels {#topic_45CF1C6A783B4F96ABF6317EAB6A854F}

[!UICONTROL マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効]化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。

チャネル作成時のガイドラインは次のとおりです。

* すべての訪問者が適切なチャネルに分類されるように、すべてのチャネルの一覧を作成し、事前に計画を立ててください。
* 常に[内部](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947)ヒットのカテゴリ用のチャネルと、[直接](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A)ヒットのカテゴリ用のチャネルを含めてください。

[!UICONTROL マーケティングチャネル]ページへのチャネルの追加は、[マーケティングチャネルの処理ルール](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08)ページのルールの作成から独立して行うことができます。ルールを作成するときに、そのルールをチャネルに関連付けます

## マーケティングチャネルの追加 {#task_98C9D3F5DBBC4B198E0A9ED4D3891E03}

マーケティングチャネルマネージャーでマーケティングチャネルを追加します。

>[!NOTE]
>
>チャネルを削除することはできません。使用しないチャネルは、無効にするか名前を変更し、後で使用するためにとっておきます。

1. **[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL レポートスイート]**&#x200B;の順にクリックします。
1. [!UICONTROL Report Suite Manager] ページで、レポートスイートを選択します。

   複数のレポートスイートを選択した場合、テンプレートから選択したレポートスイートに設定をコピーするために、テンプレートを選択する必要があります。

   詳しくは、[複数のレポートスイートへのテンプレートレポートスイート設定の適用](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC)を参照してください。

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) page displays.

1. [!UICONTROL マーケティングチャネルマネージャ] ページで、「チャネルを追加」をクリック ****&#x200B;します。

   このオプションは、チャネルが 25 個定義されている場合は利用できません。

1. Click **[!UICONTROL Save.]**
1. To configure rules for the channel, click **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08).

## Marketing Channel Manager - interface definitions {#reference_01779A2928054BF48339897D4033AFB9}

[!UICONTROL マーケティングチャネルマネージャー]ページのフィールドの定義です。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>フィールド </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>有効 </p> </td> 
   <td colname="col2"> <p>  このマーケティングチャネルの有効と無効を切り替えます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>チャネル名 </p> </td> 
   <td colname="col2"> <p>マーケティングチャネルの分かりやすい名前をつけます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ラストタッチチャネルの上書き </p> </td> 
   <td colname="col2"> <p> ラストタッチチャネルを上書きするかどうかをチャネルごとに指定できます。このチェックボックスを選択すると、すべてのチャネル（「直接」と「内部」を含む）が既存のラストタッチチャネルを上書きします。設定を変更すると、誤ったチャネル（「直接」や「内部」）にコンバージョンが関連付けられるリスクがあるので、注意が必要です。たとえば、「自然検索」チャネルを通してユーザーが以前に獲得されている場合、「直接アクセス」での訪問が発生しても、「自然検索」のチャネルがコンバージョンのクレジットを引き続き受け取るようにしたい場合は、「直接アクセス」チャネルの「ラストタッチチャネルの上書き」オプションを外しておきます（デフォルト設定のまま変更しない）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>チャネルの分類 </p> </td> 
   <td colname="col2"> <p> この値によって、チャネルを分類できます。マーケティングチャネルの分類を作成する場合、チャネル分類（サブチャネル）を追加することができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>タイプ </p> </td> 
   <td colname="col2"> <p> サイトへのユーザーの訪問手段を指定します。「<span class="uicontrol">オンライン</span>」または「<span class="uicontrol">オフライン</span>」を選択できます。検索エンジンまたは電子メールキャンペーンから来訪した訪問者に対しては「オンライン」チャネルを使用します。「オフライン」チャネルは、新聞のクーポンや雑誌の広告でサイトの情報を見つけた訪問者に使用します。オフラインチャネルには通常、データソースからインポートされたデータが含まれます。 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" scope="external" format="http">データソース</a>を参照してください。 </p> <p>See <a href="../../components/c-marketing-channels/t-offline-data.md#task_FC96E6A48F0D4D37A79BD234E90DAA26" type="task" format="dita" scope="local"> Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>色 </p> </td> 
   <td colname="col2"> <p> このマーケティングチャネルに関連付けられている色。この色は、<span class="wintitle">マーケティングチャネル</span>レポートで、このチャネルを表します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

