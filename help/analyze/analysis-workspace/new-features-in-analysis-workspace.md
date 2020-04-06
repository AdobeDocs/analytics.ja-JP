---
description: Analysis Workspace の新機能です。
keywords: Analysis Workspace
title: Analysis Workspace の新機能
topic: Reports and analytics
uuid: ff50ef9f-e5b8-442e-bfa6-2f224ba9f111
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analysis Workspace の新機能

## 2020 年 3 月

2020年3月12日にリリースされた新機能。

| 機能 | 説明 |
|--- |--- |
| Workspaceでの複数のレポートスイートのサポート | 複数のレポートスイートのデータを1つのプロジェクトに並べて表示に取り込めるようになりました。 [詳細情報...](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) |
| トレーニングチュートリアルテンプレート | この新しい標準テンプレートでは、Workspaceで初めてテンプレートを作成する際に使用する一般的な用語と手順について分析します。 これは、「新規プロジェクト」モーダルの標準テンプレートとして使用でき、リストに他のプロジェクトがない新規ユーザー向けにある、サンプルプロジェクトを置き換えます。[詳細情報...](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) |

## 2020 年 2 月

2020年2月21日にリリースされた新機能。

| 機能 | 説明 |
|--- |--- |
| デバイス間分析を使用する組織向けの新しいWorkspaceテンプレート | このテンプレートは、CDAが訪問をつなぎ合わせ、CDA専用のディメンションと指標に関する教育をどの程度効果的に行うかを示します。 CDA を使用するレポートスイートが必要です。詳しくは、[デバイス間分析の設定](https://docs.adobe.com/content/help/ja-JP/analytics/components/cda/cda-setup.html)を参照してください。 |
| Workspaceの新しいホットキー | <ul><li>すべてのパネルを折りたたむ／展開する：`alt + m`</li><li>アクティブパネルを折りたたみ／展開：`alt + ctrl + m`</li><li>左パネルを検索：`ctrl + /`</li><li>次のパネルに移動：`alt + Right Key`</li><li>前のパネルに移動：`alt + Left Key`</li></ul>[詳細情報...](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) |
| その他のWorkspaceの機能強化 | <ul><li>パネルまたはビジュアライゼーションがWorkspaceにドロップされると、左側のレールがコンポーネントに自動的に切り替わり、よりシームレスなワークフローが実現するようになりました。</li><li>テンプレートコンポーネントに対してアクションを設定できるようになりました（タグ付け、お気に入りに追加、承認など）。</li><li>フィルターを適用した指標およびセグメントリストオファーで「+」ボタンをクリックし、必要なコンポーネントが見つからない場合は、新しいコンポーネントを追加します。</li></ul> |
| Workspaceデバッガー | Workspace デバッガーがヘルプメニューに追加され、よりシームレスに有効化して Workspace リクエストをデバッグできるようになりました。[詳細情報...](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |

## 2020 年 1 月

2020 年 1 月 17 日にリリースされた新機能。

| 機能 | 説明 |
|--- |--- |
| [フリーフォームテーブルビルダー](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/freeform-table.html) | Table Builder を有効にすれば、多くのディメンション、分類、指標およびセグメントをドラッグ＆ドロップして、より複雑なビジネスの質問に回答するテーブルを作成できます。データはすぐには更新されません。Instead, updates occur after you click **[!UICONTROL Build]**, saving you time once you know what table you want to construct. さらに、この機能では次のことが可能です。<ul><li>**プレビュー**：時間をかけて実際のデータをレンダリングする前に表形式でプレビューできます。</li><li>**柔軟な行と分類の設定**：各ディメンション行に対して行と分類レベルを設定できます。以前は、Workspace で適用されたデフォルトは、データが返されるまで変更できませんでした。</li><li>**位置で分類**：ディメンション行を、_特定の項目_&#x200B;ではなく常に&#x200B;_位置で分類_（デフォルト）するように設定できます。</li><li>**手動の静的行の並べ替え**：静的な行を手動で並べ替え、必要に応じて表示できます。以前は、静的な行は指標の列またはアルファベット順でのみ並べ替えることができました。</li></ul> |

## 2019 年 10 月

2019 年 10 月 11 日にリリースされた機能強化です。

| 機能強化 | 説明 |
|--- |--- |
| フリーフォームテーブルの合計の更新 | フリーフォームテーブルに、との2つの合計が含まれるよ **[!UICONTROL Table total]** うになりまし **[!UICONTROL Grand total]**&#x200B;た。 テーブルの合計行は、適用された[レポートフィ ルター](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html)を考慮します。以前は、セグメントのみが合計に影響を与えていました。[詳細情](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html)<br/>報さらに、お **[!UICONTROL Show Totals]** よびオ **[!UICONTROL Show Grand Total]** プションがに追加されまし **[!UICONTROL Column Settings]**&#x200B;た。<br/>このフリーフォームの合計の変更により、依存ビジュアライゼーション（リンクされたビジュアライゼーションなど）、 **[!UICONTROL Summary Number]** CSVおよびPDFデータの書き出しと共に更新されます。 |
| 「未指定」または「なし」を削除するオプション | レポートフィルターのオプションに、「未指定（なし）」を簡単に削除する機能が追加されました。 |
| 紫色の精度コンポーネントの廃止 | 紫色の精度の時間コンポーネント（分、時間、日、週、月、四半期、年）は廃止されました。紫の時間コンポーネントは常に、オレンジ色のディメンションと同じ動作をするので、この変更によって画面や操作がシンプルになります。紫色の時間コンポーネントを以前使用したことがある場合、**何もおこなう必要はありません**。<br/>この変更により、紫のセクション **[!UICONTROL Time]** もに名前が変更されまし **[!UICONTROL Date Ranges]**&#x200B;た。 |

## 2019 年 8 月

機能強化は 2019 年 8 月 9 日にリリースされました。

| 機能強化 | 説明 |
|--- |--- |
| ドロップダウンの項目の上限が 50 から 200 に増加 | ドロップダウンフィルターに配置できる項目の最大数を 50 から 200 に増加しました。この強化は、すべての国（195）やすべての都道府県（52）をフィルターに追加するなどの状況への対応を可能にします。 |

## 2019 年 7 月

2019 年 7 月 19 日にリリースされた機能強化です。

| 機能強化 | 説明 |
|--- |--- |
| コホート分析の機能強化 | 新しい[コホート分析設定](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.html)が追加されました。 <ul><li>割合のみを表示</li><li>割合を整数に四捨五入</li><li>割合の平均行を表示</li></ul> |
| 過去 18 ヶ月の項目を表示 | 左側のレールに、_過去 18 ヶ月の項目を表示_&#x200B;するためのオプションが追加されました。以前は、ルックバック期間は最大 6 ヶ月でした。これにより、昨年のページやキャンペーンとの比較が簡単になります（最大 18 ヶ月前）。 |
| 新しい Analysis Workspace テンプレート | Analysis Workspace に[「Magento：マーケティングとコマース」](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html)という新しいテンプレートが追加されました。Magento e コマースのお客様向けに特別に設計されたものですが、小売業者のお客様は独自のインサイトを業務に役立てることができます。 |

## 2019 年 6 月

機能強化は 2019 年 6 月 14 日にリリースされました。

| 機能強化 | 説明 |
|--- |--- |
| そのまま使用できる新しいフィルター | 左側のレールの検索に新しい事前設定済みのフィルターが追加されました。現在表示できるもの（ディメンション、指標、承認済みなど）以外に、計算指標、顧客属性、eVar、Prop、ビデオなどの新しいフィルターが追加され、必要なコンポーネントを探すのがより簡単になります。 |

## 2019 年 5 月

2019 年 5 月 10 日にリリースされた機能強化。

| 機能強化 | 説明 |
|--- |--- |
| フロービジュアライゼーション設定に新しい設定を追加しました：繰り返しインスタンスを含める。 | [フロー設定](/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md) |

## 2019 年 4 月

2019 年 4 月 12 日にリリースされた機能強化。

| 機能強化 | 説明 |
|--- |--- |
| 最適化のベストプラクティスの強化 | [パフォーマンスの最適化](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md) |

## 2019 年 1 月

2019 年 1 月 18 日にリリースされた新機能および機能強化。

| 機能 | 説明 |
|--- |--- |
| [コホート分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | コホート分析の主な改善：<ul><li>セグメントを含む指標と戻り指標を個別に適用します。 </li><li>保持の代わりにチャーンを表示する。</li><li>待ち時間テーブル(インクルージョンイベントの前後の経過時間)を表示します。</li><li>コホートディメンションをカスタマイズします(訪問者を時間だけでなくeVarに基づいてグループ化する場合)。</li><li>ローリングコホート計算を実行する：元のコホートではなく直前の期間からのリテンション／チャーンを計算します。 </li><li>セグメントの適用に加え、インクルージョンフィールドとリターンフィールドに複数の指標を追加できます（計算指標はサポートされません）。</li></ul> |
| [表示密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | この新しい設定を使用すると、左側のパネル、フリーフォームテーブルおよびコホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。プロジェクト／プロジェクト情報および設定から利用できます。 |
| [Attribution IQ における複数値の変数のサポート](attribution-iq.md) | Analytics の一部のディメンションでは、1 回のヒットに複数の値（listVar、product 変数、listProp、マーチャンダイジング eVar など）を含めることができます。Analysis Workspace において、このような変数にヒットレベルで Attribution IQ を適用できるようになりました。 |
| パフォーマンスの向上 | 分類のビジュアライゼーションの速度改善 — 分類が多いプロジェクトの読み込みが速くなりました。 |

## 2018 年 11 月

2018 年 11 月 2 日にリリースされた新機能および機能強化。

| 機能 | 説明 |
|--- |--- |
| [VRS およびプロジェクトのキュレーション - 機能強化](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md) | これらの変更は 2018 年 10 月に実際に導入されました。キュレーションされた Workspace プロジェクトおよびキュレーションされた仮想レポートスイート（VRS）で、管理者および非管理者が表示できるコンポーネントに対して変更が加えられました。<br>以前は、「すべてのコンポーネントを表示」をクリックすると、誰でもキュレーションされていないコンポーネントを表示できました。更新されたキュレーション機能により、どのコンポーネントを表示できるかをより詳細に制御できます。</br> |

## 2018 年 10 月

2018年10月12日にリリースされた新機能および機能強化です。

<table id="table_3DDC812B2F66416F868004416D248BF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>パネルのドロップダウン管理</b> </p> </td> 
   <td colname="col2"> <p>パネルのドロップダウンの管理にいくつかの変更を加えました。これは9月のMRに導入されました。 ドロップダウンを右クリックすると、 </p> 
    <ul id="ul_4BDEC66EEB2243628FE32B43E377E5BD"> 
     <li id="li_EF8277BE972540D3B2604D82BC7C0918">ドロップダウンを削除します（このオプションは常に表示されます）。 </li> 
     <li id="li_6A991208F2744274817DBE1E9D1B443F">ラベルを削除します（ラベルが表示されている場合）。 </li> 
     <li id="li_5C1CFC465C2E41D2B35E8841EFDC82AA">追加ラベル（ラベルが表示されていない場合） </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>パネルとビジュアライゼーションのツールチップ内のリンク</b> </p> </td> 
   <td colname="col2"> <p>パネルとビジュアライゼーションのツールチップに、関連するビデオおよびドキュメントへのリンクを追加しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 9 月

2018 年 9 月 14 日にリリースされた新機能および機能強化。

<table id="table_137719BFA03C44A78FDE872DF8B228A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>パネルのドロップダウン</b> </p> </td> 
   <td colname="col2"> <p>パネルのドロップゾーンにドロップダウン機能が追加されました。 ドロップダウンを使用すると、エンドユーザーは制御された方法でプロジェクト内のデータを操作できます。 例：国別のバージョンを提供するプロジェクトに複数のバージョンがあるとします。レポート これで、これらのプロジェクトを1つのプロジェクトに折りたたみ、代わりに国のドロップダウンに追加できるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>カラーパレット</b> </p> </td> 
   <td colname="col2"> <p>異なるカラーパレットを選択するか、独自のパレットを指定することで、Workspace で使用されるカラースキームを変更できるようになりました。これは、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。変更の概要、フ <b>リーフ</b> ォームテーブルの条件付き書式、およびマップのビジュアライゼーションには影響しません。 </p> <p>注記：カラーパレットのサポートは、Internet Explorer 11 に対して有効ではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>新規テンプレート: Audio Consumption</b> </p> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/ja_JP/sc/appmeasurement/hbvideo/media-workspace-templates.html"  >Audio Analytics</a> を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>
## 2018 年 8 月

2018 年 8 月 10 日にリリースされた新機能および機能強化。

<table id="table_DD77C02344414DCD9AC0A6A22E648B72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>ドロップゾーンガイド</b> </p> </td> 
   <td colname="col2"> <p>これらのガイドは、ドラッグ＆ドロップの各アクションでどんなことができるかを、より簡単に理解できるように手助けをします。例えば、列にマウスオーバーする際には、追加、置換、フィルター基準、分類などを表示します。 </p> <p>また、2 つの指標を積み重ねる（無効なデータの原因となります）など、非推奨または禁止アクションをおこなっている場合に警告する黄色／赤のガイドも追加しました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>空追加白パネルオプション</b> </p> </td> 
   <td colname="col2"> <p>パネルの追加を簡単にするため、開始パネルの下に「+」記号を追加しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 7 月

2018 年 7 月 20 日にリリースされた新機能および機能強化。

<table id="table_336E121310204DC492EA004F40830B0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="attribution-iq.md"  > Attribution IQ </a> </b> </p> </td> 
   <td colname="col2"> <p>Attribution IQ は、マーケティングパフォーマンスについて、さらに高度でインテリジェントな分析を実現します。新しいアトリビューションモデルは、分析ワークスペース（任意のテーブルまたは任意の分類）の指標および計算指標で使用できます。 新しい属性パネルでは、ビジュアライゼーションと比較機能が強化されました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> 左側のパネルの改善 </b> </p> </td> 
   <td colname="col2"> <p>左側のパネルが改善され、さらに直観的で使いやすくなりました。 </p> 
    <ul id="ul_087BEDF4338946DA857CD82CB69F98C2"> 
     <li id="li_C751AACAC60442DC93118F0819F8EEA7"> コンポーネント（指標、セグメント、日付）の作成(+)関数をヘッダーとインラインで使用できるようになりました。 </li> 
     <li id="li_DE2EB184A02D4CE58C23F518DB85EFDD"> 各セクションのリストの下部に「+すべてを表示」を追加し、5つ以上のオプションがあることを確認しました。 </li> 
     <li id="li_5208F3C6026647B09F4A85131B175175">コンポーネントが選択されたときに、アイコン付きの表面アクション（タグ、お気に入りなど）。 </li> 
     <li id="li_11E601488A844515928231E09889BC54">ユーザーインターフェイスの美的な改善を行いました。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>計算指標の合計 </b> </p> </td> 
   <td colname="col2"> <p>可能な場合は、割合を含む計算指標の合計が表示されるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>新しい日 <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  > 付範囲プリセ </a>ット </b> </p> </td> 
   <td colname="col2"> <p>「過去13週間」を、分析ワークスペースの日付範囲プリセットに追加しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 6 月

2018 年 1 月 15 日にリリースされた新機能および機能強化。

<table id="table_57035A06D99447A6BE6ED825A648ED3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md"  > 動的ディメンション列 </a> </b> </p> </td> 
   <td colname="col2"> <p>以前は、ディメンションが列にドロップされた場合、非時間ディメンションの上位5つの値（および時間ディメンションの場合は15）を表示し、これらの値を静的に保っていました（つまり、選択された5つの値は変更されませんでした）。 </p> <p>今後は、デフォルトでは静的な値ではなく動的な値が表示されるとともに、静的な値に変更するオプションも用意されます。その他の注意事項： </p> 
    <ul id="ul_C802BC32CB084E30B4E58E9E90B9A63D"> 
     <li id="li_452466AB416F4737B532849C604BD4CC">動的ディメンションの(i)をクリックすると、ランク（5つのうち上位1つ）とディメンションタイプが表示されます。 </li> 
     <li id="li_588F6199E38D47869AC855A4C2A4D1B7">データが更新されると、動的ディメンション列が更新され、現在の5/15ディメンション項目が表示されます。 </li> 
     <li id="li_19D47638D4D94416B0DAD2B2FB835ABE">コピーまたは移動される動的ディメンション列は静的になります。 </li> 
     <li id="li_B95411689AE04774B7B9BA128F2DB96F">静的ディメンション列にカーソルを重ねると、そのディメンションが静的であることを示す鍵のアイコンが表示されます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>新しい Workspace 機能が表示されるモーダル </b> </p> </td> 
   <td colname="col2"> <p>先月導入された今日のヒントと同様、新規リリース後に初めて Workspace にログインする際に、Workspace の新機能についての情報がこのモーダルに表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 5 月

2018 年 5 月 11 日にリリースされた新機能および機能強化。

<table id="table_EE4C690A178B4F80BDAF2BB4424D6020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>今日のヒント</b> </p> </td> 
   <td colname="col2"> <p>インターフェイスの右下隅に「今日のヒント」（短いビデオと共に）が表示されます。 以下のヒントは、多数の優れた分析ワークスペース機能を理解するためのものです。 <span class="uicontrol">ヘルプ</span>／<span class="uicontrol">ヒント</span>から、いつでもヒントを解除、または利用可能にすることを選択できます。 </p> <p><img  src="assets/tip_of_day.png" width="300px" id="image_44A2AA712E4242EC92A180380E66AD7D" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >セグメントテンプレート</a>と<a href="/help/analyze/analysis-workspace/components/apply-create-metrics.md"  >計算指標テンプレート</a></b> </p> </td> 
   <td colname="col2"> <p>左側のパネルには、セグメントテンプレートと計算指標テンプレートが表示されるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>コンポーネントのドラッグ中にスクロール可能</b> </p> </td> 
   <td colname="col2"> <p>コンポーネントを新しい位置にドラッグしながら、上下にスクロールできるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>異常値に関する追加情 <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md"  > 報 </a></b> </p> </td> 
   <td colname="col2"> <p>折れ線グラフの異常値の上にカーソルを置くと、異常値の日付と生の値が情報に表示されるようになりました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 4 月

2018 年 4 月 13 日にリリースされた新機能および機能強化。

<table id="table_B9E784CD14A1453EB360FCCDC612250F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  >「ヘッダーテキストを折り返し」がデフォルトで有効</a> </p> </td> 
   <td colname="col2"> <p>フリーフォームテーブルの列設定で、「<span class="uicontrol">ヘッダーテキストを折り返し</span>」がデフォルトで有効になりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md"  >新しい行設定</a> </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">行ごとに割合を計算</span>という新しい設定により、フリーフォームテーブルでは、列ではなく行全体のセルの割合が表示されるようになります。これは、あるディメンション値が他の値に対してどの程度公正であるかを経時でトレンド分析する場合など、割合のトレンド分析に特に役立ちます。<span class="uicontrol">視覚化</span>アイコンをクリックした場合、これはデフォルトでオンになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B"  >「100％の積み重ね」ビジュアライゼーション設定</a> </p> </td> 
   <td colname="col2"> <p>積み重ね面／積み重ね棒／積み重ね横棒グラフのビジュアライゼーションを 100％の積み重ねに変更する新しい設定が追加され、相対的な比率を確認できるようになりました。 </p> <p><img placement="break"  src="assets/stacked_100_percent.png" width="500px" id="image_ED9C94CE5EAF4500B1EF71BE8701B6D2" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/virtual-analyst/overview.md"  >異常値検出と貢献度分析</a>は、現在、Analysis Workspace からのみ使用できます。 </p> </td> 
   <td colname="col2"> <p>異常値検出と貢献度分析は、Reports &amp; Analytics の画面から削除され、現在は、Analysis Workspace からのみ使用できます。 </p> <p>Adobe Analytics Select および Adobe Analytics Foundation をご利用のお客様は、Workspace で「毎日の精度」の異常値検出のみにアクセスできます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 3 月

2018 年 3 月 9 日にリリースされた新機能および機能強化。

<table id="table_580CF2C1322E4FB78870BE2B1F497B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > ヘッダーテキストの折り返し </a> </p> </td> 
   <td colname="col2"> <p>ヘッダーを読みやすく、またテーブルを共有しやすくするため、フリーフォームテーブルでヘッダーテキストを折り返せるようになりました。「ヘッダーテキストを折り返し」というオプションが「列設定」に追加されました。これは、特に .pdf のレンダリングや名前の長い指標に使用すると便利です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/apply-create-metrics.md"  > 右クリックメニューから指標を作成 </a> </p> </td> 
   <td colname="col2"> <p>計算指標をすばやく簡単に作成できるように、フリーフォームテーブルの右クリックメニューに「<span class="uicontrol">選択から指標を作成</span>」が追加されました。このオプションは、ヘッダー列のセルが 1 つ以上選択されると表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  > マップビジュアライゼーションの機能強化 </a> </p> </td> 
   <td colname="col2"> <p>マップのビジュアライゼーションで前期（前年比など）比較を表示できるように、次の機能が強化されました。 </p> 
    <ul id="ul_F570E6AB174C45788620CF50E2742A08"> 
     <li id="li_746E329037764644A9CCF79161C26350">マップのビジュアライゼーションで負の数を表示できるようになりました。 例えば、前年比指標のグラフを表示するときに、ニューヨークの上に「-33％」と表示することができます。 </li> 
     <li id="li_E05F0380627044E6A4E8A60C98494BF7">「パーセント」タイプの指標では、クラスタリングは割合を平均化します。 </li> 
     <li id="li_44C04306EA1B413E91B8256B340D5296">新しいカラースキーム：正/負（緑/赤） </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > カスタムテンプレートのアップデート </a> </p> </td> 
   <td colname="col2"> <p>最近リリースされたカスタムテンプレートに関しては、 </p> 
    <ul id="ul_787F48253F454163B99F6DD50F199FE2"> 
     <li id="li_828DD547DDB54A81B9FFB9FE92790F6C">プロジェクトの上部（タイトルの近く）にテンプレートアイコンを追加し、テンプレートの編集モードがプロジェクトの出発点として使用されていないことを区別できるようにしました。 </li> 
     <li id="li_EEAA4D115CB74A57BABD524B2561E0CC">Analysis Workspace でプロジェクトを作成／キュレーション権限が与えられている場合に、管理権限なしでWorkspaceプロジェクトテンプレートの作成（別名保存）と編集をおこなえるようになりました（<span class="ignoretag"><span class="uicontrol">管理者</span>／<span class="uicontrol">ユーザー管理</span>／<span class="uicontrol">グループ</span>／<span class="uicontrol">すべてのレポートアクセスを編集</span>／<span class="uicontrol">Analytics ツールをカスタマイズ</span>／<span class="uicontrol">Analysis Workspace でプロジェクトを作成／キュレーション</span></span>）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 2 月

2018 年 2 月 9 日にリリースされた新機能および機能強化。

<table id="table_824BBE4A554B4DB092ADA9044383D0FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md#create-custom-template"  > カスタム Workspace テンプレート </a> </p> </td> 
   <td colname="col2"> <p>独自の Workspace テンプレートを作成して保存することで、組織内の他のユーザーが自身の関連するデータを使用して作業を開始することができるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > 新規プロジェクト開始モーダル </a> </p> </td> 
   <td colname="col2"> <p>「新規プロジェクト」をクリックすると、新しい画面が開き、次のどこから開始するかを選択できるようになりました。 </p> 
    <ul id="ul_FE90E6B9AF334A029D66A43901F8FA0B"> 
     <li id="li_F1DFD9AE140C4E5B849D4C522D5968DB">空白のプロジェクト </li> 
     <li id="li_23BD391D68674C299858A97BFE10598B">標準の（組み込みの）ワークスペーステンプレート、または </li> 
     <li id="li_04D84FE375B84BF88843AA0D43A234BF">カスタムワークスペーステンプレート（上記を参照） </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>右クリックでのコピーのサポート </p> </td> 
   <td colname="col2"> <p>セルやテーブルを一貫してコピーできるように、右クリックの「クリップボードにコピー」オプションが追加されました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  >列の割合に対する改善</a> </p> </td> 
   <td colname="col2"> <p>列に表示される全体に占める割合は、シナリオによっては行が全体の 100 ％を超える場合（平均値など）であっても、上限が 100 ％に制限されていました。 </p> <p>100%を超える割合がより正確に表示されるようになりました。 また、列の幅が大きすぎる場合に、上限を1,000%に移動します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md#section_3DD847151DA14914888A70FC4FD7BDFB"  > 分類における条件付き書式の有効化 </a> </p> </td> 
   <td colname="col2"> <p>「カスタム」制限を選択した場合を除き、フリーフォームテーブルに適用した条件付き書式（色など）が分類で自動的に有効となります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>デフォルトの<a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  >カレンダー</a>ビューの変更 </p> </td> 
   <td colname="col2"> <p>デフォルトでは、Workspaceカレンダーに、現在の月と次の月ではなく、現在の月と先月が表示されるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Workspaceテーブルのホバー/選択時の色の改善 </p> </td> 
   <td colname="col2"> <p>フリーフォームテーブルのセルの上にカーソルを置いた場合とセルをクリックした場合の色の違いがより明確になりました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2018 年 1 月

2018 年 1 月 19 日にリリースされた新機能および機能強化。

<table id="table_7A2E678577F94BDABB1276C826E6554F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>フリーフォームテーブルの他のディメンション項目の<a href="/help/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md"  >フィルタリングオプション</a> </p> </td> 
   <td colname="col2"> <p>（既存の「次を含む」オプションと「次を含まない」オプションの他に）ディメンション項目の次の（アドバンス）フィルターオプションが追加されました。 </p> 
    <ul id="ul_869B3E943E304C0282D56AD96BB79E18"> 
     <li id="li_81A49BA0CA3041C7AB892FAD2D129E5A">すべての語句を含む </li> 
     <li id="li_2AB564F917844F82839A91949D0B684A">いずれかの語句を含む </li> 
     <li id="li_16C7938EDC8F422EA006FB63F2881EF1">このフレーズを含む </li> 
     <li id="li_5130EBE9A7A54CCFA313F3C3C268B367">いずれの語句も含まない </li> 
     <li id="li_861825154EDC49EBA57514FD0A2AE462">このフレーズを含まない </li> 
     <li id="li_5364BFB73ECF4B92A6663693ABD4BCF5">次に等しい </li> 
     <li id="li_1EBF3119B6364842A35D39BAD645F4AF">等しくない </li> 
     <li id="li_487886E0A6EC4245A0E85D2E8B4A20FB">次で始まる </li> 
     <li id="li_A73F54DFBAAB44D4A4134342A3124E47">次で終わる </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>  パネルやプロジェクトをまたがった<a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_05B7914D4C9E443F97E2BFFDEC70240C"  >ビジュアライゼーション／パネルのコピー＆ペースト</a> </p> </td> 
   <td colname="col2"> <p>ビジュアライゼーションまたはパネルを右クリックしてコピーし、その要素をプロジェクト内の別の場所または別のプロジェクトに貼り付け（「挿入」）できるようになりました。 </p> <p>この機能を使用して、「構築ブロック」（事前定義されたビジュアライゼーション/パネル）を作成し、他のプロジェクトにコピーして、ビジネスに固有のデータを使用して、より迅速に開始できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  >「メッセージング」および「ロケーション」に関する新しい Mobile テンプレート</a> </p> </td> 
   <td colname="col2"> <p>2 つの新しいプロジェクトテンプレートが追加されました。 </p> 
    <ul id="ul_2F5976C849474A2B8A6BCDA2559F2855"> 
     <li id="li_51B7830E062A4CFDBDF219C56249A733">アプリ内およびプッシュメッセージのパフォーマンスに重点を置いた、「メッセージング」用の新しいモバイルプロジェクトテンプレートです。 </li> 
     <li id="li_D2FB258EF3AF4EB19CEB258D08F4EBBE">「ロケーション」用の新しいモバイルプロジェクトテンプレート。マップに場所のデータが表示されます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>列のサイズ変更の改善 </p> </td> 
   <td colname="col2"> <p>左端の列のサイズを変更する場合、Workspaceで残りの列の幅の割合が維持されるようになりました（右端の列の幅を調整するだけではありません）。 この変更により、テーブルの作成が高速化され、分析と共有の両方が可能になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テーブルに <a href="/help/analyze/analysis-workspace/visualizations/freeform-table.md"  >400 行</a>を表示 </p> </td> 
   <td colname="col2"> <p>1 つのテーブルに 400 行を表示できるようになり（変更前は 200 行）、365 日間のトレンドに対応するようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>  PDF での<a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  >マップビジュアライゼーション</a>のサポート </p> </td> 
   <td colname="col2"> <p>2017 年 10 月に導入されたマップビジュアライゼーションを、PDF でも表示できるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > プロジェクトをコピー／名前を付けて保存する際の相対的内部リンク</a> </p> </td> 
   <td colname="col2"> <p>以前は、プロジェクトをコピーした場合や「名前を付けて保存」をおこなった場合、プロジェクト内に保存されている内部リンクはすべて、コピーされたプロジェクトではなく、元のプロジェクトを指していました。 </p> <p>コピー／名前を付けて保存の後でも、内部リンクは内部のプロジェクトに対して相対的になりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>貢献度分析：<a href="https://marketing.adobe.com/resources/help/ja_JP/analytics/contribution/ca_main.html"  >トークン通知 </a> </p> </td> 
   <td colname="col2"> <p>会社に含まれる貢献度分析トークンの数が限られている場合、分析ワークスペースのUIに、トークンを使用する際に通知が表示されるようになりました。 これにより、残りのトークン数を把握できます。  </p> <p>（管理者ユーザーは、グループ権限を編集することにより、トークンの使用者を制限できます。この権限は、<span class="uicontrol">Analytics</span>／<span class="uicontrol">管理者</span>／<span class="uicontrol">ユーザー管理ホーム</span>／<span class="uicontrol">グループの編集</span>／<span class="uicontrol">全レポートアクセスを編集</span>／<span class="uicontrol">レポートスイートツールをカスタマイズ</span>／<span class="uicontrol">ツールとレポート</span>では「異常値検出と貢献度分析」と呼ばれています。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>マルチバイ文字を含むCSVファイル </p> </td> 
   <td colname="col2"> マルチバイト文字を含む電子メール送信されたCSVファイルをMS Excelで開くことができるようになりました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>イベント番号、eVar#、prop#の変更 </p> </td> 
   <td colname="col2"> <p>2017 年に左側のパネルのディメンション名に追加された event#、eVar# および prop# は、コンポーネントを<b>検索</b>するときにのみ表示されます。 </p> <p>（仮想レポートスイートビルダーにも適用）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>なし/未指定の変更 </p> </td> 
   <td colname="col2"> <p>Reports &amp; Analytics、セグメントビルダーおよび分析ワークスペースのディメンション値メニューと一致するように、分析ワークスペースでの「なし」と「未指定」の機能の仕組みを変更しました。 </p> <p>つまり、Workspaceのほとんどのプロジェクトで、値が「なし」ではなく「未指定」と表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 11 月

2017 年 11 月 10 日にリリースされた新機能。

<table id="table_C502E81253634E6CBAE7F12C7B62F7B6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>リストの互換性のないコンポーネント </p> </td> 
   <td colname="col2"> <p>場合によっては、プロジェクトに含まれていないコンポーネントがレポートスイートに含まれることがあります。 その場合（プロジェクトの読み込み時またはレポートスイートへの切り替え時）に表示される「互換性のないレポートスイート」メッセージに、互換性のないコンポーネントのリストが表示されるようになりました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 10 月

2017年10月27日にリリースされた新機能。

<table id="table_892279F2B4AF4DB38C64AA9AFC5657A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  > マップのビジュアライゼーション </a> </p> </td> 
   <td colname="col2"> <p>Analysis Workspace での新しいマップのビジュアライゼーションでは、位置データを持つ顧客インタラクションを簡単にビジュアライズできます。マクロ（グローバル）ビューからミクロ（市区町村）ビューまで、ビジュアライゼーションの様々な階層レベルを簡単にズームインおよびズームアウトして、複数の地域にわたるデータを確認できます。 </p> <p>非モバイルデータセットの場合は IP アドレスを使用して位置データを視覚化したり、Mobile SDK を使用しているお客様の場合は緯度と経度のデータを Analysis Workspace に取り込んだりできます。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/line.md"  > トレンドビジュアライゼーションの精度セレクター </a> </p> </td> 
   <td colname="col2"> <p>データソースのディメンションが時間ディメンションの場合、時間の精度を簡単に切り替えることができるようになりました。 ビジュアライゼーション設定のドロップダウンから精度を切り替えることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > セグメントドロップゾーンの拡張：フルディメンションおよびイベント </a> </p> </td> 
   <td colname="col2"> <p>以前は、セグメントドロップゾーンには、ディメンション項目、日付範囲またはセグメントのみをドロップできました。 セグメントドロップゾーンに完全なディメンションまたはイベントをドロップできるようになりました。 どちらの場合も、分析ワークスペースでは「存在する」ヒットセグメントが作成されます。 </p> <p>例：「eVar1が存在するヒット」または「イベント1が存在するヒット」。 </p> <p>注意：計算指標をセグメントゾーンにドロップすることはできません。セグメントゾーンにドロップできるのは、セグメントを作成できるディメンションまたは指標だけです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md"  > データソース設定に一覧表示される接続済みのビジュアライゼーション </a> </p> </td> 
   <td colname="col2"> <p>フリーフォームまたはコホートテーブルにビジュアライゼーションが接続されている場合、左上の点（データソース設定）に接続されたビジュアライゼーションがリストされるようになりました。 リンクされたビジュアライゼーションをホバーするとハイライト表示され、クリックすると表示されます。 </p> <p>また、データテーブルの表示/非表示を切り替える「データテーブルを表示/非表示」チェックボックスもあります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > 左側のパネルのイベント名に追加されたイベント番号表示 </a> </p> </td> 
   <td colname="col2"> <p>2017 年 10 月より前に、evar の番号および prop の番号がディメンション名に追加され、これらの番号を使用して検索できました。同じ機能がイベントにも </p> <p>例：「サブスクリプション」という名前のイベントは、左側のパネルに「サブスクリプション（event1）」と表示されます。 </p> <p>注意： </p> 
    <ul id="ul_5DF85C65F7004539949DDC4F23922296"> 
     <li id="li_A685834B4914460D87568583BB39C474">イベント番号は、（タイトルを短くするために）テーブルに表示されません。 </li> 
     <li id="li_D742D04470244633900335B7F5A79FD9">一貫性を保つために、propとeVarもテーブル内に数値を表示しなくなりました。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  >デフォルトで論理順序で並べ替えられる事前設定済みディメンション</a> </p> </td> 
   <td colname="col2"> <p>一部の標準ディメンションのデフォルトの並べ替え順は、次の場合に更新されました。 </p> 
    <ul id="ul_B9C0C761F39E43A4977EC028F4D4525C"> 
     <li id="li_FE72ADDCD32A4FF7907462726D6E7758">フリーフォームテーブルにドラッグされたとき。 </li> 
     <li id="li_5D78DD0DCB7347AC85E260F53109010C">左側のパネルに表示される場合。 </li> 
    </ul> <p>例えば、「時間帯」がテーブルにドロップされる場合、午前 00 時～午後 11 時の順に並べ替えられます。指標の列で並べ替えを行うオプションは引き続きあります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md"  > 信頼区間でチャートを再調整するオプション </a> </p> </td> 
   <td colname="col2"> <p>異常値検出の信頼区間では、ビジュアライゼーションの Y 軸を自動的に調整しないので、わかりやすくなります。 </p> <p>これで、信頼区間でグラフを拡大・縮小できるオプションが得られました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-alerts/alert-manager.md"  > アラート：「<b>更新</b>」オプションの追加 </a> </p> </td> 
   <td colname="col2"> <p>アラートマネージャーで、1 つまたは複数のアラートを選択して「<span class="uicontrol">更新</span>」をクリックすると、これらを更新できます。 </p> <p>これにより、元の有効期限に関係なく、「<span class="uicontrol">更新</span>」がクリックされた日から 1 年先に有効期限日が延長されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UIの改善 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_645B43AC6F554353B887DD58F0AA86E8"> 
     <li id="li_05B16A84008E4DA3A5DE91AF3C942D55">空のパネル：マップ、フォールアウト、フロー、ヒストグラム、コホート、ベンなど、パネルに追加できるすべてのビジュアライゼーションをハイライト表示して、開始を終了しました。 このパネルをデフォルトのプロジェクト開始状態として保存するオプションがあります。 </li> 
     <li id="li_9F1ED138DB0E453DA6BD4B4A512492CC">左側のパネルのスタイルが新しくなり、パネル、ビジュアライゼーション、コンポーネントが見やすく、使いやすくなりました。 </li> 
     <li id="li_5DF6177F0EFD4D4D9D432768DEA3F37D">フリーフォームテーブル：空のフリーフォームテーブルで、アニメーションGIFが表示され、Adobe Workspaceのドラッグ&amp;ドロップの枠組みを示すようになりました。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 9 月

2017年9月22日にリリースされた新機能。

<table id="table_DC0DA93B8A3B481080FCB2BA8F985753"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md"  >Analysis Workspace の時間分割ディメンション</a> </p> </td> 
   <td colname="col2"> <p>タイムスタンプに基づくディメンションが、Timestamp Workspaceに追加されました。 次のディメンションが含まれます。 </p> 
    <ul id="ul_9BDBC0B344504E85840040E493873A47"> 
     <li id="li_826A8CBF4FDB4C98AC176C7145C09DB2">時間帯（例： 01、12、15、23） </li> 
     <li id="li_FD6AAD4D3F544224A757D8124F973BE5">午前/午後（例： AM PM） </li> 
     <li id="li_5CAE35FB8E3E490A8FCF72DF8AC619CC">曜日（例：月、火曜日、水曜日など） </li> 
     <li id="li_930DFC6BFCC740A392EC7FA859FF0E73">週末/平日（例：週末、平日） </li> 
     <li id="li_C09F8BF8C598498392732C183C5BB720">月の日付(例： 1、2、.... 30, 31) </li> 
     <li id="li_E80A8932C32B4410A9BC703090FB5CFF">年の月（例：1月、2月、3月） </li> 
     <li id="li_67620F09B58244B2B17317E0DB97067A">年の日（例：1日目、2日目など） </li> 
     <li id="li_A96CD77357064FC19D92EFA8244560D6">四半期（第1四半期、第2四半期など） </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > フリーフォームテーブル内で一度に複数の列を管理 </a> </p> </td> 
   <td colname="col2"> <p>複数の列の設定を一度に変更できるようになりました。 複数の列を選択し、その列のいずれかの設定アイコンをクリックします。 行った変更は、セルが選択されているすべての列に適用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > フロー：ディメンション間のラベル付け </a> </p> </td> 
   <td colname="col2"> <p>各フロー列の先頭の新しいディメンションラベルにより、フローのビジュアライゼーションで複数のディメンションをより直感的に使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477"  > ヒストグラムの「ヒット」カウント方法 </a> </p> </td> 
   <td colname="col2"> <p>以前は、ヒストグラムのビジュアライゼーションには2つのカウント方法がありました。訪問と訪問者（デフォルト）。 </p> <p>3つ目のカウント方法「ヒット」をセグメントコンテナとして使用できます。 フリーフォームテーブルの y 軸指標として、「回数」が使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>  セグメント比較および貢献度分析設定の「<span class="uicontrol">すべてクリア</span>」ボタン </p> </td> 
   <td colname="col2"> <p>以下の Workspace 領域において、各要素を手動で削除する代わりにすべての要素をクリアできるようになりました。 </p> 
    <ul id="ul_73E06D64CDCA4E83B9FEC2FD99D41CD3"> 
     <li id="li_A51EF8FADFA04CC19FD79C1675597659"> <a href="/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC"  > 貢献度分析の除外されたコンポーネント </a> </li> 
     <li id="li_30E612D5A7584484967260931DB9E30E"> <a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"> セグメント比較の除外されたコンポーネント </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/summary-number-change.md"  >変更概要表示タイプの名前の更新</a> </p> </td> 
   <td colname="col2"> <p>現在の2つの「変更概要」オプションの名前が変更され、意味が明確になりました。 </p> 
    <ul id="ul_7301D1C73E72424F911EE8DAAD9247A0"> 
     <li id="li_89D94632E0C94263A84887AF5B360E27">変更を表示/変更率を表示 </li> 
     <li id="li_D48EB4055019449DAF2998CB9A5D23DF">差異を表示/生の差異を表示 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/summary-number-change.md"  >短縮された数値の概要／変更概要の小数点以下の桁数の拡張</a> </p> </td> 
   <td colname="col2"> <p>以前は、概要番号の略式化/変更ビジュアライゼーションに小数点以下の桁数が0個表示されていました。 </p> <p>小数点以下の桁数を0 ～ 3桁まで選択して、レポートを向上 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 8 月

2017年8月18日にリリースされた新機能。

<table id="table_C29887097C894B1C91AD7086F0DAEC73"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > 保存中のプロジェクトのタグ付け </a> </p> </td> 
   <td colname="col2"> <p>プロジェクトの保存中にプロジェクトにタグ付けできるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md"  > プロジェクト一覧ページのタグ列 </a> </p> </td> 
   <td colname="col2"> <p>Workspace のプロジェクト一覧ページに<span class="wintitle">タグ</span>列を追加しました。この列には、各プロジェクトに設定されたタグが表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > フロービジュアライゼーションの .CSV ファイルでの書き出し </a> </p> </td> 
   <td colname="col2"> <p>フロービジュアライゼーションを .csv ファイルとしてダウンロードできるようになりました。これにより、フロー結果を Microsoft Excel（テーブルとして表示）またはその他のツールで分析できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-alerts/intellligent-alerts.md"  > インテリジェントアラート：信頼レベルの追加 </a> </p> </td> 
   <td colname="col2"> <p>異常値検出ベースのアラートの場合、2つの新しい信頼性レベル（99.75%と99.9%）が追加されました。 一部の精度の選択のデフォルトも変更されました。 </p> 
    <ul id="ul_EB1F07A4D2204D57B2DDD9838CE4F5D9"> 
     <li id="li_542AAACE703F4EBFBD91F11F5ABC2929">時間別：現在は99.75% </li> 
     <li id="li_D01E4598FB33473FAAC5D60441FD081B"> 日別：現在99% </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 7 月

2017年7月21日にリリースされた新機能。

<table id="table_64E3A9960F314E2F9FFC738696EACDF7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/visualizations/text.md"  > リッチテキストエディター </a></b> </p> </td> 
   <td colname="col2"> <p>テキストボックスビジュアライゼーションおよびパネル／ビジュアライゼーションの説明内でフォント設定（太字、斜体など）およびハイパーリンクを設定できるようになりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><a href="/help/analyze/analysis-workspace/analysis-workspace-features.md#section_253EA04E067F4A29A8B54CE2B7631086"  >イントラリンク（クイックビジュアライゼーションリンク）</a></b> </p> </td> 
   <td colname="col2"> <p><b>イントラリンク</b> (Intra Linking)を使用すると、プロジェクト内の特定のパネルやビジュアライゼーションに、テキストボックスからリンクダウンして、プロジェクトの目次を作成できます。 プロジェクトリンクを共有するのと同じように、プロジェクト内の特定のビジュアライゼーションやパネルを他の人と共有することができます。「パネルリンクを取得」および「ビジュアライゼーションリンクを取得」という新しい右クリックオプションが追加されました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_94F1988CB4B9434BA1D9C6034062C3DE"  > 凡例ラベルの編集 </a></b> </p> </td> 
   <td colname="col2"> <p>ビジュアライゼーションの凡例（フォールアウト、領域、積み重ね面、棒グラフ、棒グラフ、ドーナツグラフ、ヒストグラム、横棒グラフ、横棒グラフ、積み重ね面グラフ、折れ線グラフ、散布図、ベン図）の系列名を変更して、ビジュアライゼーションをより消耗させます。 </p> <p>凡例の編 <b>集は</b> 、次に適用されないツリーマップ、箇条書き、変更の概要または数値、テキスト、フリーフォーム、ヒストグラム、コホートまたはフローのビジュアライゼーション。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><a href="/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md"  >「データソースを管理」の更新</a></b> </p> </td> 
   <td colname="col2"> <p>（ビジュアライゼーションに使用する）データソースの管理方法を改善しました。データソースをテーブルにロックする際に、別々の非表示のテーブルが存在しなくなりました。 </p> <p>代わりに、作成元のテーブルにビジュアルを結び付けておきます。 また、ライブリンクテーブルのバグも解決されます。このバグでは、精度を変更し、次のプロジェクト読み込み時に古い精度に戻ります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md"  > 特定の異常値をハイライトする機能 </a></b> </p> </td> 
   <td colname="col2"> <p>貢献度分析内の青い点で異常値を強調表示し、その異常値にリンクされたインテリジェントアラートプロジェクトを作成します。 これにより、分析された異常値がより明確に示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Experience Cloud ログインの「プロジェクトリンクを取得」</b> </p> </td> 
   <td colname="col2"> <p>以前は、Experience Cloud 資格情報でログインして Analytics に移動すると、<span class="ignoretag"><span class="uicontrol">共有</span>／<span class="uicontrol">プロジェクトリンクを取得</span></span>の機能を使用できませんでした。この問題を修正しました。このオプションを使用するには、その前にプロジェクトを保存する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><a href="/help/analyze/analysis-workspace/curate-share/schedule-projects.md"  >スケジュール済みプロジェクトマネージャーの「期限切れのプロジェクト」フィルター</a></b> </p> </td> 
   <td colname="col2"> <p>スケジュールされたプロジェクトマネージャーで、期限切れのプロジェクトをフィルタリングできるようになりました。 その後、これらのプロジェクトを再起動するか、削除するかを決定できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 6 月

2017年6月8日にリリースされた新機能。

<table id="table_5B859A64363A44A98FC55E7AFB3C1D0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md"  > フォールアウト</a></b>機能の強化 </td> 
   <td colname="col2"> 
    <ul id="ul_8A979BC0BE0F4D008F68B019A2D83A08"> 
     <li id="li_C8093834980B43A094FA9E2A7906E135">無制限のセグメントを比較 </li> 
     <li id="li_45D709C9B04F4E6A9BD94FD03E0C80FA">タッチポイントグループの命名と管理（追加、削除、移動など）が容易 </li> 
     <li id="li_BC609CDFD9AA4EB081987922DB318040">右クリックして「<span class="uicontrol">トレンドタッチポイント（%）</span>」を選択：合計フォールアウト数の割合のトレンドを追跡します。 </li> 
     <li id="li_C72BB725368644DDA3FCE479A918CDB3">右クリックして「<span class="uicontrol">すべてのタッチポイント（%）のトレンドを追跡</span>」を選択：同じチャート上のフォールアウト（「<span class="wintitle">すべての訪問</span>」が含まれている場合はこれを除く）で、すべてのタッチポイントの割合のトレンドを追跡します。 </li> 
     <li id="li_40D0A8B481B04F21BEC0A4E421C77865">パス内の次のヒットまで（最後までではなく）個別のタッチポイントを抑制する機能 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md"  > <b>フロー</b> </a>機能の強化 </td> 
   <td colname="col2"> 
    <ul id="ul_54675DB3F59E4B24AF0C8F6E6AB2F3C1"> 
     <li id="li_DEF7D9BF03CD4A2D86A4BDD89FB3731A">「<span class="wintitle">ラベルの切り捨てを無効化</span>」という新しいビジュアライゼーション設定が追加されました（デフォルト = オフ）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  > カレンダーの変更</a></b> </td> 
   <td colname="col2"> カレンダーを変更して、Reports &amp; Analyticsカレンダーに合わせます。 
    <ul id="ul_BD706B07369F4339BF4925F22FEC1C7F"> 
     <li id="li_33A47BAAD3C04C8784D2FC00A6F6782E">最初のクリックで開始した日付範囲が選択されます。 次に、2回目のクリックまでどちらの方向でも範囲をハイライト表示し、日付範囲の終わりを選択します。 Shiftキーを押しながら（または右クリックして）最初の日付をクリックすると、範囲に追加されます。 </li> 
     <li id="li_C3BEC56ABCED482C82A41EA0550B3077">様々な周期的な日付要素の長期的なルックバック期間（例：最長2年間の日数の遡及が可能） </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>ディメンション項目の検索の改善</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_E955585818FF4553A869003B94DDB697"> 
     <li id="li_A37D2DB6290842578FE752DD8E712B73">速度の向上 </li> 
     <li id="li_BADFD0FF3D574F1C8F19EFB37F95969C">必要に応じてより多くのデータを取り込める「<span class="uicontrol">過去 6 ヶ月の上位の項目を表示</span>」オプション </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  >「割合制限を使用」チェックボックス</a></b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_7B6B794EDF874A4D87770AB9BAB42F33"> 
     <li id="li_0B403D892320434FBAD9A7F7B808947C"> 割合による切り取りを示すチェックボックスを追加しました。特に、割合に基づく指標の場合は、このチェックボックスがオンになりました（割合に基づかない指標の場合も機能します）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>コンポーネントマネージャの </b>強化 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_BB22F84ABFB04685A9752AD4BDE6E60A"> 
     <li id="li_B3D460C15C454911A9D7254F50815355">アラートおよびスケジュールされたプロジェクトの有効期限の追加 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/components/c-alerts/alert-manager.md"  > アラートマネージャー</a> </b>機能の強化 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_72464DC499744290BA37DB3B1E143F74"> 
     <li id="li_C687F0A3A99F4CC39B482BDA0F7B75DD">アラートを有効／無効にする機能が追加されました。 </li> 
     <li id="li_F7415EE7DF29417FAF416594E36A38A4">「有効／無効」列が追加されました。 </li> 
     <li id="li_61B3A60A2AFB4BD0AA4D83803AB95B1E">有効/無効のアラートのフィルタを追加。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>New <b> <a href="/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md"  > Hotkeys </a></b> </p> </td> 
   <td colname="col2"> <p>以下のホットキーが追加されました。 </p> 
    <ul id="ul_5AE965D910DA4883BC2067CDFDBBA75A"> 
     <li id="li_6DBD6DFB9CA54F89B9A0627F3B1D5928">Alt + Shift + 1 =パネルペインに移動 </li> 
     <li id="li_1B7E7C1115A84DB8A1BC07EA1C3AB15F">Alt + Shift + 2 =ビジュアライゼーションパネルに移動 </li> 
     <li id="li_1BDB09DDEEDC4E7DB0D1C08A4E02A613">Alt + Shift + 3 =コンポーネントペインに移動 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 4 月

2017 年 4 月 21 日にリリースされた新機能。

<table id="table_53EEFB870ED943F5BFD71FAB2DBCE49B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > 人物テンプレート </a> </p> </td> 
   <td colname="col2"> <p>注意：人物テンプレートとそれに関連する人物指標は、<a href="https://marketing.adobe.com/resources/help/ja_JP/mcdc/mcdc-people.html"  >Adobe Experience Cloud Device Co-op</a> の一部としてのみ使用可能です。 </p> <p>テンプレートは、重複を排除した実訪問者数指標に基づいています。この指標は、個別訪問者数指標です。 人物指標は、消費者がブランドと関わる際にどのくらいの頻度で複数のデバイスを使用しているかを測定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「取り消し/やり直し」オプションの改善 </p> </td> 
   <td colname="col2"> <p>これらのリストは、Workspace Workspaceで取り消し/やり直しがで <a href="/help/analyze/analysis-workspace/build-workspace-project/undo-redo.md"  > きる操作とできない操作を分析しま </a>す。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 2 月

2017年2月17日にリリースされた新機能：

<table id="table_227D3668E9FD4FF4A1906FC619DCAFBF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md"  > 位置で分類 </a> </p> </td> 
   <td colname="col2"> <p>テーブルの位置による分類を許可します。例：「常にフリーフォームテーブルの上位 7 行を分類したい」フリーフォームテーブルを作成する際に、「位置で分類」を有効にするチェックボックスが追加されました。 この設定は、デフォルトでは無効になっています。 </p> <p>以前は、分類の値のリストはレポート作成の時点で「ロック」されていました。例えば、<span class="wintitle">日付</span>を<span class="wintitle">ページ</span>ごとに分類した場合、選択した日付範囲の上位 50 ページのリストが表示されていました。 </p> <p>そのレポートを保存して 1 ヶ月後に実行した場合、上位 50 ページが変動している可能性があるものの、ただし、分析ワークスペースは、元の分類の結果と同じページを返し、現在の月が日付範囲として返された結果を「信頼」します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2017 年 1 月

2017年1月20日にリリースされた新機能：

<table id="table_0AB06B81BFA34521A9BF1150E64663C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  >プロジェクトを保存することなく PDF を送信およびダウンロード</a> </p> </td> 
   <td colname="col2"> <p>プロジェクトを保存しなくても、WorkspaceでPDFを送信およびダウンロードできるようになりました。 PDFファイルの名前は、プロジェクトの現在の名前と一致します。 ダウンロードしたPDFには、プロジェクトの未保存の変更が含まれます。 未保存のプロジェクトはスケジュールできないことに注意してください。 （未保存のCSVファイルを送信およびダウンロードすることもできますが、スケジュールを設定することはできません）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/curate-share/curate.md"  >プロジェクトコンポーネントの自動共有</a> </p> </td> 
   <td colname="col2"> <p>すべての受信者とプロジェクトのコンポーネント（セグメント、計算指標および日付範囲）を自動的に共有するオプションが用意されるようになりました。共有すると、これらのコンポーネントは受信者のWorkspace のコンポーネントドロップダウンに表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CSV形式のフォールアウトビジュアライゼーション </p> </td> 
   <td colname="col2"> <p>CSV形式のフォールアウトビジュアライゼーションのサポートを追加しました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > セグメント内の日付範囲 </a> </p> </td> 
   <td colname="col2"> <p>日付範囲は、セグメントドロップゾーン（例えば、パネルセグメントドロップゾーン、フォールアウトビジュアライゼーションセグメントドロップゾーンなど）にドロップできます。 それらの日付範囲はセグメントに自動変換されます。日付範囲は、カスタムおよび非カスタムに設定できますが、時間/日/週/月/四半期/年のような精度は設定できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > テーブルの各列に期間を追加 </a> </p> </td> 
   <td colname="col2"> <p>テーブルの各列に期間を追加できるようになり、カレンダーで設定されている期間とは異なる期間を追加できるようになりました。 この機能は、日付を比較する別の方法です。 また、各列の日付を同じ行のすべての開始に揃えることもできます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2016 年 11 月

2016年11月11日にリリースされた新機能：

<table id="table_9B2B9CC7A3574A99A716BF1C9745E32B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 日付の比較 </a> </p> </td> 
   <td colname="col2"> <p>新しい日付比較機能を使用すると、任意の列を使用して、次のような一般的な日付比較を作成できます。前年比、前四半期比、前月比など。 </p> <p>日付比較には、割合の変化を示す「差異」列が自動的に含まれます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2016 年 10 月

2016年10月21日にリリースされた新機能：

<table id="table_56258080C60F480AA83E1D5DE7D2C782"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 新機能 </th> 
   <th colname="col2" class="entry"> 使用方法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  > フォールアウト分析 </a></b> </td> 
   <td colname="col2"> <p>新しいフォールアウト機能により、マーケティングファネル機能が分析ワークスペースに追加されます。 ファネルを使用すると、顧客がマーケティングキャンペーンを放棄した場所や、Webサイトやクロスチャネルキャンペーンとの対話中に、定義済みのコンバージョンパスからそれた場所を特定できます。 フォールアウト分析を使用すると、新しいビジュアライゼーションと、主要成功指標のコンバージョンを識別するために分析ワークスペースが提供する固有の柔軟性を備えた堅牢なファネルを構築できます。 フォールアウト分析を使用すると、 </p> <p> </p> 
    <ul id="ul_E7C8255BA5D84F74ABBC6CC0E148DFB0"> 
     <li id="li_B7AC104F2A9348DCB2BCAA2FC9D3F3E6">ファネルステップ（タッチポイント）のドラッグ、ドロップおよび並べ替え </li> 
     <li id="li_CC85524BC64546CD84794CC02C24CF21">複数次元のフォールアウトの分析（異なるディメンションや指標の値を組み合わせる） </li> 
     <li id="li_FA59CEE0211E4894B9109FF6A2FA3F80">フォールアウト直後に顧客がどこに移動したかを知るための次のステップを特定する </li> 
    </ul> <p><img placement="break"  src="assets/fallout2.png" width="500px" id="image_193B0E7870734DAFA063BBFA121A3E34" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > フロービジュアライゼーション </a></b> </td> 
   <td colname="col2"> <p>新しいフロー機能を使用すると、分析ワークスペースの新しい更新された柔軟なビジュアライゼーションを通じてサイト/アプリを表示し、顧客のサイト/アプリ内での移動と進行を把握できます。 フローを使用すると、 </p> <p> </p> 
    <ul id="ul_F1D4A99743664CB3B17E9485CF5E72FC"> 
     <li id="li_0F7AF953EAB746DC95032FF9A533E560">資産を通じた顧客の遍歴を視覚化 </li> 
     <li id="li_697A47BE06CF4284ACA3DBE4CA4012BF">顧客の遍歴の入口、出口または特定のディメンション項目から、すぐに次のステップを分析する </li> 
     <li id="li_D13AD928AC434D599D43836FB334B14D">選択したパスの特定のポイントを指定して、ユーザーのセグメントを動的に作成します。 </li> 
    </ul> <p><img placement="break"  src="assets/flow.png" width="500px" id="image_8ED88B5EDAA046978170F8BBB4018DA2" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><a href="/help/components/c-alerts/intellligent-alerts.md"  >インテリジェントアラート</a></b> </td> 
   <td colname="col2"> <p>Adobe Analytics 全体の新しいアラートシステムであるインテリジェントアラートでは、アラートプレビューとルール貢献度を備えた Analysis Workspace 内でアラートの作成と管理をおこなうことができます。次のことができます。 </p> <p> </p> 
    <ul id="ul_02BD64D3047942009880B8F1DA1F2A40"> 
     <li id="li_01504AABBC514DF38354683843222541">異常値（90％、95％または 99％のしきい値、変化率、超過／未満）に基づいたアラートの構築。 </li> 
     <li id="li_9BFE2B4C429D441287F1A37A08E62A40">アラートがトリガーされる頻度のプレビュー。 </li> 
     <li id="li_08D310196581483DB499C00358835B73">自動生成される Analysis Workspace プロジェクトへのリンクが記載された電子メールまたは SMS によるアラートの送信。 </li> 
     <li id="li_2ADF9465EE474CDB839ED867662CCE6F">1 つのアラートで複数の指標を示す「積み重ね」アラートの作成。 </li> 
    </ul> <p><img placement="break"  src="assets/intel-alerts.png" width="400px" id="image_10069C33B6B1437CA578B8194FC75AD8" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md"  > 異常値検出と貢献度分析 </a></b> </td> 
   <td colname="col2"> <p>トレンドデータにおける変化が有意な場合に、その旨とその原因を通知します。 </p> <p>異常値検出と貢献度分析の双方が、Analysis Workspace の主要ワークフローになりました。 </p> <p>重要：貢献度分析は、Adobe Analytics Premium のお客様のみご利用いただけます。 </p> <p>次のことができます。 </p> <p> </p> 
    <ul id="ul_9CEE47788F3640838D8598F2E2C020D6"> 
     <li id="li_787236BB5EA545B8833B311C06C24337">データの統計的に有意なデータの異常値を自動的に検出します。 </li> 
     <li id="li_2FB3D94DEEF14DD5ADA6AD69E15F243D">貢献度分析を毎日の異常値に対して実行し、それを分析ワークスペースプロジェクトに埋め込みます。 </li> 
    </ul> <p><img placement="break"  src="assets/anomaly_linechart.png" width="500px" id="image_DFAF4034E2AC4B4AAB140EA004112722" /> </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > スタータープロジェクト </a></b> </td> 
   <td colname="col2"> 分析ワークスペースの使い始めを簡単にするために、次のような一般的なビジネス上の問題に対応する、事前にビルドされたプロジェクトテンプレートを作成しました。 <p> </p> 
    <ul id="ul_603F5ACC16F74D53AEB9F762FAC91656"> 
     <li id="li_6B3F2E5D4B044EC19D45E5501E33DB91">ユーザー保持率 </li> 
     <li id="li_7240EE8852FC4642B3AD4837C990A775">モバイルアプリの獲得 </li> 
    </ul> <p><img placement="break"  src="assets/starter.png" width="500px" id="image_A62AFD39812E43DCBF30D5E072A7E892" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md">ヒストグラムビジュアライゼーション</a></b> </td> 
   <td colname="col2"> <p>ヒストグラムを使用すると、ユーザーは成功したユーザーの分布を確認できます。イベント グループとグループのサイズをカスタマイズして、配布に合わせたり、価値の高いユーザーと価値の低いユーザーを特定したりできます。 </p> <p><img placement="break"  src="assets/histogram3.png" width="500px" id="image_E3277073B50140E0A3FD7C1601CF9661" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> その他の更新 </td> 
   <td colname="col2"> 
    <ul id="ul_2585F74DC7754C819017F280E16BF06F"> 
     <li id="li_412446013E7F42DBB1BF50F9E2C4D92F"> 
      <!--AN-124610: -->プロジェクトレベルの設定として、「繰り返しインスタンスをカウント」を追加しました（<span class="uicontrol">プロジェクト</span>／<span class="uicontrol">プロジェクト情報および設定</span>）。この設定は、繰り返しインスタンスをレポートでカウントするかどうかを指定します。 同じ変数に対して複数の連続する値がある場合は、それらを1つの変数として、または複数の変数のインスタンスとしてカウントできます。 </li> 
     <li id="li_480E1B307C62418CBC2F50ADE32B9EE9">カレンダーの「キャンセル」と「実行」の横に、「すべてのパネルに適用」という新しいボタンが追加されました。 「実行」を「適用」に変更しました。 新規ボタンをクリックすると、現在のパネルだけでなく、プロジェクト内の他のすべてのパネルで選択した日付範囲が変更されます。 </li> 
     <li id="li_4D10DFE307344D06AA60792FABE5B57E"> 
      <!--AN-124168: -->左側のナビゲーションパネル上に、タグ、お気に入り、承認、<b>共有（新規）</b>、削 <b>除（新規）</b>。 </li> 
     <li id="li_946EC05568D4447193E9307546DF6F9B">検索バーに、タグ、お気に入り、承認済みの項目、およびコンポーネントをフィルターできるフィルターを追加しました。 </li> 
     <li id="li_4EA118ACCD3B4F88B0ECF72717F631FA">セグメント、指標、日付範囲をプレビューできるプレビューアイコンを手動の行(リストディメンション項目を含む動的な行ではない)に追加しました。 </li> 
     <li id="li_81D5241EA3FD49CEA0E9F412837D87A8"> 
      <!--AN-128702: -->Analysis Workspace のチュートリアルの YouTube リンクを <a href="https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS"  >https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS</a> に更新しました。 </li> 
     <li id="li_D81DB98C49664D2884CCCC1DB0058CD8"> 
      <!--AN-124004:-->ビジュアライゼーションで、「<span class="uicontrol">やり直し</span>」という右クリックオプションをコンテキストメニューに追加しました（フロー、ベン、ヒストグラムで動作します）。現在のビジュアライゼーションの設定は削除され、設定し直すための新しいパネルが開きます。 </li> 
     <li id="li_84632BFCE1794B49A31FF45067FA04B7">「凡例を表示」という新しいビジュアライゼーション設定では、数値の概要／変更概要ビジュアライゼーションのフィルター詳細テキストを隠すことができます。 </li> 
     <li id="li_EE8C48642DD54A04B08F4222F9565BF6">変更概要ビジュアライゼーションの新しいビジュアライゼーション設定では、「差異を表示」で 2 つの割合から表示を選択できます。割合以外の数値で「差異を表示」を選択すると、数が表示されます。 </li> 
     <li id="li_17AAABCA7B3A477182FB70453CA2EEBB">時間ディメンションの行数を調整しました。 </li> 
     <li id="li_35A91D50CD514CD0B939C24AEEC64BF4">セグメントビルダーの左側のナビゲーションパネルのルックアンドフィールが変更され、計算指標ビルダーが Analysis Workspace と似た外観になりました。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 2016 年 6 月

2016 年 6 月 17 日にリリースされた新機能：

* [管理者がユーザーの](https://marketing.adobe.com/resources/help/ja_JP/reference/groups.html) 「/」タブへのアクセスを許可または拒否できる新しいグ **[!UICONTROL Analytics]** ループ権 **[!UICONTROL Workspace]** 限が追加されました。 2016年6月17日現在、すべてのユーザーがこのタブにアクセスする権限を持っています。 アクセスを拒否するには、ユーザーをワークスペースアクセスグループの分析から削除するだけです。
* The [Segment Comparison Panel](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)discovers the most statistically significant differences between any two segments through an automated analysis of every single metric and dimension you have access to.
* [トップメニューを再配置し](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) 、拡張性を高める新しいプロジェクトメニュー構造。 例えば、新しいコホートパネルを作 **成する場合** 、空のパネルを作成し、コホートテーブルのビジュアライゼーションをドラッグする必要があります。
* [新しい左側のパネル](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)：パネル、ビジュアライゼーションおよびコンポーネント
* 最大 3 セグメントおよび 1 つの指標をドラッグして、ベン図を作成できる新しい[ベン図のビジュアライゼーションタイプ](/help/analyze/analysis-workspace/visualizations/venn.md)。
* ランク付けされたテーブルの[トレンド選択](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)（折れ線グラフ）がリンクされました。
* [ビジュアルを作成アイコン](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)：このアイコンをクリックすると、次の操作がインテリジェントに推測されます（棒グラフ、ベン図など）。
* 拡張さ [れた手動行](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) 機能
* [追加セグメントドロップゾーン](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)
* マイナーアップデート：

   * パネル内のすべてのビジュアライゼーション、およびプロジェクト内のすべてのパネルを削除できるようになりました（以前は、少なくとも 1 つのビジュアライゼーションか 1 つのパネルを維持する必要がありました）。
   * Analysis Workspace での作業を簡潔化する[ショートカットキー](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)（ホットキー）が変更されました。
   * スタイルの変更：ビジュアライゼーションのフォントが小さくなり、行のカラースウォッチが追加され、パネルの日付選択機能が下に移動されました。

## 2016 年 4 月

2016年4月22日にリリースされた新機能：

<table id="table_2649645FDED84B71952F741ABB3FC20E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ファイルの送信 </td> 
   <td colname="col2"> <p>電子メールを使用して Analysis Workspace を送信したり、Analysis Workspace の配信をスケジュールしたりします。<a href="/help/analyze/analysis-workspace/curate-share/t-schedule-report.md"  >ファイルの送信 - プロジェクトの配信スケジュールの設定</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PDF のダウンロード </td> 
   <td colname="col2"> <p>アクションメニューから、分析ワークスペースプロジェクトをPDF形式（CSV形式でのダウンロードと同様）でダウンロードできます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 2016 年 1 月

2016年1月22日にリリースされた新機能。

* [操作を元に戻す](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_12890C393D5E4FC8A3CF050318BD8482)
* [このプロジェクトへのリンク](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_453E70F7409F4501B8E976A0D18C9A46)
* [ブレットグラフ、散布図、ツリーマップビジュアライゼーション](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_B19EA50EBF5546E99D3A142827153FD6)
* [セグメント、指標、日付に名前を付けて保存](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_04C8B10A0751453AAE5F1BC35938C6CE)
* [「新しいセグメントを追加」ボタン](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_85CC88C02C79456EA2B41F2BFBB64FC4)
* [条件付き書式](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_5775B505D83041408B8C3EAEC5D7C32B)
* [ディメンションプレビュー](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_F519EBF889B244E8B25BB6BA2833325A)
* [凡例を表示](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_28D10D86CAE343AB838808C1DD2E7983)
* [Y 軸をゼロに固定](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_83DF5DE79EF04F9F8DCB3154F5E799B3)
* [タブタイトルのプロジェクト名](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_497C61A030984BCCA2CEA553312C3226)
* [プロジェクト所有権の転送](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_989C2CCB80B5408EB85E6B12C8D943E3)


## 操作を元に戻す {#section_12890C393D5E4FC8A3CF050318BD8482}

Analysis Workspace でおこなったほとんどの操作を元に戻すことができるようになりました。

To undo, click **[!UICONTROL Undo]** from the action menu.

![](assets/undo.png)

また、Windows および Mac の標準の[キーボードショートカット](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)（Ctrl または Command + Z）を元に戻すこともできます。

*`Undo`*&#x200B;は、テーブルの分類操作を元に戻す場合に特に便利です。

取り消し可能でない&#x200B;*`not`*&#x200B;アクション：

* Changing the configuration of a [!UICONTROL Cohort Table] (such as dragging metrics, changing values). ただし、をクリックした後でをク **[!UICONTROL Undo]** リックできま **[!UICONTROL Run]**&#x200B;す。

* パネルとサブパネルのサイズ変更または移動

取り消し履歴をクリアするアクション：

* プロジェクトの保存
* レポートスイートの変更を参照してください。

## このプロジェクトへのリンク {#section_453E70F7409F4501B8E976A0D18C9A46}

In a project, click **[!UICONTROL Link to This Project]** from the Actions menu to email a saved project&#39;s URL to other users. 管理受信者は、この方法で共有されたプロジェクトを編集して保存できます。 それ以外の場合、これらのプロジェクトは読み取り専用です。

![](assets/link-to-this-project.png)

>[!NOTE]シングルサインオン（従来のシングルサインオンと、Experience Cloud を介したログイン）を使用している企業では、レポートリンクの共有機能を利用できません。

## ブレットグラフ、散布図、ツリーマップビジュアライゼーション {#section_B19EA50EBF5546E99D3A142827153FD6}

2016年1月のリリースでは、次の新しいビジュアライゼーションを利用できます。

**箇条書きグラフ**

目的の値が他のパフォーマンス範囲（目標）と比較または測定される様子を確認できます。

![](assets/bullet-image.png)

黒丸グラフは、1つの主要な指標（例えば、現在の年次累計売上高）を特徴とし、その指標を他の1つ以上の指標と比較して意味を豊かにし(例えば、ターゲット売上高と比較)、高、中、低などの質的な範囲のパフォーマンスのコンテキストで表示します。 You can specify goal ranges in [!UICONTROL Visualization Settings].

**散布図**

![](assets/scatter.png)

表示されたインプレッション数と、そのインプレッションを閲覧した個別ユーザー数を表示します。 各データポイントのサイズは、ビューアが広告に公開された平均回数を視覚的に示します。 サイズとデータは、選択したディメンション、日付範囲およびフィルターによって異なります。

>[!NOTE]散布図に関連付けられたテーブルには、少なくとも 2 つの列が必要です。最初の列はX軸を定義し、2番目の列はY軸を定義します。 3番目の列がある場合、散布図はそれを使用して点の半径を決定します。 つまり、列 *1*、*2*、*3* は、*X 軸*、*Y 軸*、*点の半径*&#x200B;に対応します。

**ツリーマップ**

階層（ツリー構造）のデータをネストされた長方形のセットとして表示します。 ツリーの各分岐に長方形が割り当てられ、サブ分岐を表す小さな長方形で並べられます。

![](assets/treemap.png)

色とサイズの寸法がツリー構造と何らかの形で相関している場合、特定の色が特に関連しているなど、他の形で見分けにくいパターンを簡単に見ることができます。 ツリーマップの2つ目の利点は、構築によってスペースを効率的に使用できることです。

## セグメント、指標、日付に名前を付けて保存 {#section_04C8B10A0751453AAE5F1BC35938C6CE}

When editing an existing (saved) segment the Analysis Workspace Segment Builder, click **[!UICONTROL Save As]** to make a copy.

![](assets/segment-save-as.png)

The new segment displays in the [!UICONTROL Segments] group in the [!UICONTROL Components] panel.

*`Save As`* とも使用でき [!UICONTROL Calculated Metric Builder] ます [!UICONTROL Date Range Builder]。

## 「新しいセグメントを追加」ボタン{#section_85CC88C02C79456EA2B41F2BFBB64FC4}

The **[!UICONTROL Add New Segment]** button has been added to the location where you drag-and-drop segments onto a project.

![](assets/add-new-segment.png)

This enhancement is helpful if you prefer to directly create segments when working in a project, rather than using the [!UICONTROL Segment] panel to create segments.

## 条件付き書式 {#section_5775B505D83041408B8C3EAEC5D7C32B}

「列の設定」で、セルのデータに条件付き書式を適用できます。

![](assets/conditional-formatting.png)

<table id="table_4285E6982FBD4B66AC95AAF6C5C7B347"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 条件付き書式 </td> 
   <td colname="col2"> <p> データ値に基づいて、次の色をセルに適用します。 </p> 
    <ul id="ul_97E3AD5F6B41460C882D8B4EE0A8C77A"> 
     <li id="li_88874B4250224DE781C03E4A5931D6A2">緑：高い値 </li> 
     <li id="li_B4863F967C7544D7AA2847696FB85525">黄色：中点値 </li> 
     <li id="li_5B06D7CD0C39437898DA55EA653A1124">赤：低い値 </li> 
    </ul> <p>テーブルのディメンションを置き換えると、条件付き書式の制限がリセットされます。指標を置き換えると、その列の制限が再計算されます（指標が X 軸、ディメンションが Y 軸で示される場合）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自動生成 </td> 
   <td colname="col2"> <p>条件付き書式の制限を自動的に生成します。 上限は、この列の最大値です。 下限は最も低く、中間点は上限と下限の平均です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> カスタム </td> 
   <td colname="col2"> <p>条件付き書式の「<span class="uicontrol">上限</span>」、「<span class="uicontrol">中間点</span>」、「<span class="uicontrol">下限</span>」の各フィールドに手動で値を割り当てることができます。これにより、どのような場合に列の値が良好、平均的、望ましくないと判断されるかを柔軟に決定できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ディメンションプレビュー {#section_F519EBF889B244E8B25BB6BA2833325A}

In the [!UICONTROL Dimensions] component panel, you can hover over the information icon next to a dimension and see a top-five preview.

![](assets/dimension-preview.png)

## 凡例を表示 {#section_28D10D86CAE343AB838808C1DD2E7983}

このオ [!UICONTROL Visualization Settings] プション **[!UICONTROL Legend Visible]** で、ビジュアライゼーションの凡例の表示/非表示を切り替えます。

![](assets/legend-visible.png)

## Y 軸をゼロに固定 {#section_83DF5DE79EF04F9F8DCB3154F5E799B3}

線グラフおよび面グラフの数値によっては、Y 軸の一番下がゼロでないことがあります。でを有 **[!UICONTROL Anchor Y Axis at Zero]** 効に [!UICONTROL Visualization Settings] すると、Y軸が強制的にゼロになり、より正確なトレンドの表示が得られます。 次の例は、この設定が有効および無効になっている場合の売上高グラフの変化を示しています。

**「Y軸をゼロで固定」が無効**

![](assets/anchor_Y_axis_off.png)

**「Y軸をゼロで固定」を有効にする**

![](assets/anchor_Y_axis.png)

## Project Name on Tab Title {#section_497C61A030984BCCA2CEA553312C3226}

プロジェクトを保存する際、ブラウザータブのタイトルは、「`<Project Name>` - Analysis Workspace」のように表示されます。この機能強化は、複数のブラウザータブで複数のプロジェクトを開く場合に役立ちます。

## プロジェクト所有権の転送 {#section_989C2CCB80B5408EB85E6B12C8D943E3}

管理者は、あるユーザーから別のユーザーに [!UICONTROL Analysis Workspace] プロジェクトを転送できます。

//に移動し **[!UICONTROL Admin]** て、プ **[!UICONTROL User Management]** ロジェク **[!UICONTROL Transfer]** トを転送します。
