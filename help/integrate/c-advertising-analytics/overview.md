---
description: 'null'
title: Advertising Analytics の概要
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Advertising Analytics の概要

Advertising Analytics では、すべての Google および Bing 有料検索データを並べて表示できます。以前は、Google AdWords／DFA　または Microsoft Bing Ads のデータは、いずれも Adobe Advertising Cloud または Google／Bing で表示する必要がありました。現在 Adobe Analytics では、インプレッション数、クリック数、コスト、品質スコア、平均順位を、検索エンジンおよび AMO ID インスタンス（クリックインスタンス）から直接取得できるようになりました。

>[!NOTE] Yahoo Gemini は、2019 年 3 月 31 日に Microsoft Bing に吸収されました。その結果、Yahoo Gemini 広告アカウントオプションは使用できなくなりました。

これらの検索エンジンのデータをAdobe Analyticsで統合することで、分析ワークスペースの機能を使用して同じデータを分析できます。 A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

この統合は、次のオーディエンスです。

* 有料検 **索マーケタ** ーのパフォーマンスレポートを収集する必要があるアナリスト。
* 次の質 **問に対して回答を求める有料検索** マーケティング担当者。サイトに送信するトラフィック量と顧客のコンバージョン率はどの程度か。 コスト効率に優れた広告キャンペーン

## 前提条件 {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/jp/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* この機能は、Advertising Cloud以外のお客様とAMO以外のお客様で使用できます。
* Advertising Analyticsにアクセスするには、Adobe Analytics管理者である必要があります。 その後、管理者以外の [ユーザーに](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) 、アクセス権限を付与できます。
* Google／Bing の検索データを表示する Analytics レポートスイートは、[Experience Cloud 組織にマッピングされている](https://marketing.adobe.com/resources/help/ja_JP/mcloud/report-suite-mapping.html)必要があります。
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* GoogleアカウントIDやパスワードなど、Adobe Analyticsと統合する検索アカウントに対する編集権限を持つユーザーに対するログイン資格情報が必要です。
* Bing広告の場合は、Bing顧客IDも必要です。
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) for any of the three search engines. 代わりに、他のWebブラウザーを使用します。

## Advertising Analytics の権限 {#section_FCC58EB635954A32990D4E67B52B4369}

Analyticsには、Analytics管理者に自動的に付与される2つの権限があります。 管理者は、これらの権限を管理者以外のユーザーに付与することを選択できます。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 権限 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> Adobe Analytics内での権限の付与 </th> 
   <th colname="col4" class="entry"> Adobe Experience Cloudにログインしている場合は権限を付与 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 管理 </p> </td> 
   <td colname="col2"> <p>ユーザーが広告検索アカウントを設定/編集/表示できます。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> 管理者</span>／<span class="uicontrol">ユーザー管理</span>／<span class="uicontrol">グループ</span>／<span class="uicontrol">全レポートアクセスの編集</span>／<span class="uicontrol">Analytics ツールのカスタマイズ</span>／<span class="uicontrol">Advertising Analytics 管理</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Adminconsole.adobe.com にログイン</span>／<span class="uicontrol">製品</span>／<span class="uicontrol">製品プロファイル</span>／<span class="uicontrol">「権限設定」タブ</span>／<span class="uicontrol">Analytics ツール</span>／<span class="uicontrol">Advertising Analytics 管理</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 設定 </p> </td> 
   <td colname="col2"> <p>ユーザーは、Advertising Analytics用にプロビジョニングされるレポートスイートを設定できます。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> 管理者</span>／<span class="uicontrol">ユーザー管理</span>／<span class="uicontrol">グループ</span>／<span class="uicontrol">全レポートアクセスの編集</span>／<span class="uicontrol">レポートスイートツールのカスタマイズ</span>／<span class="uicontrol">Advertising Analytics 設定</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Adminconsole.adobe.com にログイン</span>／<span class="uicontrol">製品</span>／<span class="uicontrol">製品プロファイル</span>／<span class="uicontrol">「権限設定」タブ</span>／<span class="uicontrol">レポートスイートツール</span>／<span class="uicontrol">Advertising Analytics 管理</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Analytics のディメンションと指標 {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analyticsは、次のディメンションと指標を分析ワークスペース、Reports &amp; Analytics、Report BuilderおよびAnalyticsレポートAPIに追加します。

**ディメンション**

>[!IMPORTANT]
>
>この統合では、AMO ID 変数の分類によって新しいディメンションセットが作成されます。これらの新しいディメンションは、既存のマーケティングチャネルやキャンペーン追跡変数ディメンションに影響を与えたり、変更したりしません。 AMO IDは、訪問者が有料検索広告からサイトにランディングした場合に、訪問者のプロファイルに接続されます。 したがって、AMOディメンションは、この統合で提供されるAMO指標と、訪問者(訪問数、訪問者数、ページ表示数、直帰率、注文数、売上高、カスタムイベントなど)で下流に収集されるデータの両方を分類するために使用できます。 また、他のオンサイト指標に関するレポート時に、他のディメンションで分類できます。
>
>これらの指標の分類は毎日更新されます。 したがって、検索エンジンでメタデータに変更を加えた場合、その変更が反映されるのは、分類が更新された翌日までです。

| 分類（ディメンション）名 | 定義 |
|--- |--- |
| キーワード一致タイプ(AMO ID) | キーワード一致タイプ。一般に、広告タイプに一致タイプがない場合、値は「部分一致」、「フレーズ一致」、「完全一致」、または「値なし」になります。 |
| 広告プラットフォーム(AMO ID) | 検索エンジン名。 Google AdWords または Microsoft Bing Ads のいずれかの値を含めることができます。 |
| アカウント(AMO ID) | 追跡する検索エンジンアカウントの名前。 |
| キャンペーン(AMO ID) | 検索エンジンのキャンペーンアカウントの名前。 |
| 広告グループ(AMO ID) | 検索エンジンキャンペーンの広告グループの名前。 |
| 広告(AMO ID) | 広告で使用される広告タイトル + 広告の説明。 |
| キーワード(AMO ID) | 検索エンジンアカウントからのキーワード値。 |
| 一致タイプ(AMO ID) | キーワードに割り当てられたキーワード一致タイプ。通常、値は部分一致、フレーズ一致、完全一致となり、広告タイプに一致するタイプがない場合は値なしです。 |
| 広告タイプ(AMO ID) | 提供される広告のタイプ。通常は「テキスト広告」です。 |
| 広告タイトル(AMO ID) | 広告で使用されるタイトルオブジェクト. |
| 広告の説明(AMO ID) | 広告で使用される広告の説明オブジェクト. |
| 広告表示URL(AMO ID) | 広告で使用される広告の表示 URL オブジェクト. |
| 広告の表示先URL(AMO ID) | 広告に割り当てられたランディングページ URL または最終的な URL. |
| ネットワーク(AMO ID) | 広告が提供されるネットワーク。 Advertising Analytics では、この値は常に「Search」です。 |
| 配置(AMO ID) | 管理対象プレースメント Web サイト (コンテンツネットワーク用)。このディメンションは管理対象プレースメントでのみ使用します。 |
| 製品ターゲット(AMO ID) | PLA 広告で使用される製品ターゲットの名前 (購入した実際の製品ではありません). |
| 最適化(AMO ID) | これは、Advertising Analyticsでは使用されません。 Advertising Cloudのお客様のみが使用します。 |
| デバイス(AMO ID) | 今日は使用されません。(実際のターゲットではなく)広告の訪問者デバイスタイプ（モバイル、デスクトップなど）を示す、将来の製品の拡張の可能性を示すプレースホルダー。 |

**指標**

>[!IMPORTANT]
>
>Advertising Analytics で利用できる指標（以下の一覧を参照）は、検索エンジンからのサマリレベルのデータです。Analytics訪問者プロファイル これらは、AMO ID変数および関連する分類ディメンションにのみ接続されます。 したがって、AMO IDディメンションに基づくディメンション以外のディメンションやセグメントによってレポートされることはありません。 これを行うと、Analyticsでデータのゼロが表示されます。 他の指標と共に計算指標に含めることもできますが、これらの計算指標もAMO IDディメンションでのみ分類する必要があります。
>
>これらの指標は毎日のデータソースなので、現在の日のデータは含まれません。 また、毎日よりも低い精度でレポートすることはできません。
>
>AMO IDがランディングページに設定された場合（クリックスルーなど）に設定されるAMO IDインスタンス指標があります。 この指標は、ランディングページのヒットでリアルタイムに取り込まれ、他のディメンションがランディングページ上で設定された分類で使用できます。

| 指標名 | 定義 |
|--- |--- |
| AMO インプレッション数 | 検索エンジンがレポートした広告インプレッションの数。 |
| AMO クリック数 | 検索エンジンからレポートされた広告のクリック数。 |
| AMO コスト | 検索エンジンがレポートする各キーワード/広告に対して支払うコスト。 |
| 平均掲載順位 | 検索エンジンからレポートされる広告の平均掲載順位を反映した計算指標。 |
| 平均品質スコア | 検索エンジンからレポートされた平均品質スコアを反映する計算指標。 |
