---
description: 'null'
seo-description: 'null'
seo-title: プロジェクトコンバーターに関する FAQ
title: プロジェクトコンバーターに関する FAQ
uuid: 8e1bf0e9- ce0f-443a- bcfe-45d3e2c82b1c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# プロジェクトコンバーターに関する FAQ

## プロジェクトコンバーターに関する FAQ {#topic_8231595303AD403E9322645A63632D57}

* [既知の変換に関する問題](../../../analyze/ad-hoc-analysis/c-aha-project-converter/aha2aw-converter-faq.md#section_39C922A58B2E49C9877B363042801361)
* [コンバージョンFAQ](../../../analyze/ad-hoc-analysis/c-aha-project-converter/aha2aw-converter-faq.md#section_1E53FE373AF045978F939916124E194E)

## Known Conversion Issues {#section_39C922A58B2E49C9877B363042801361}

| 問題 | 説明 |
|--- |--- |
| 分類または列での分単位の精度 | 分単位の精度で分類が適用されているか、または分単位の精度が列にある場合、プロジェクトはAnalysis Workspaceに変換できません。解決策として、分の精度の分類を削除して列から削除し、プロジェクトを変換します。その後、Analysis Workspaceで分単位の精度で分類を適用できます。 |
| 列セグメントとともに使用される内部計算指標 | 列セグメントとともに内部計算指標を使用している場合、プロジェクトはAnalysis Workspaceに変換できません。この問題を回避するには、コンバージョン前にプロジェクトから内部計算指標を削除してから、Analysis Workspaceに再度追加してください。 |


## Conversion FAQ {#section_1E53FE373AF045978F939916124E194E}

<table id="table_48CC119236C94835A6A512E989BE4200"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>質問：Ad Hoc Analysis の機能のうち、Analysis Workspace でサポートされないものがありますか。</b> </p> </td> 
   <td colname="col2"> <p>回答：サイト分析レポートは Analysis Workspace ではサポートされません。Ad Hoc AnalysisとWorkspaceの他のビジュアライゼーションとの間に若干の違いがあります。詳しくは、以下の質問を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：表の設定はどのように変換されますか。</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A645A004FB094A1593439A6607FE9A6B"> 
     <li id="li_033CA771F08A4BC3B0BC52CDCCA03FF4"><b>表示される行数</b>：Analysis Workspace では 1 ページに 10 行しか表示されません（一度に最大 400 行表示されるようにカスタマイズ可能）が、Ad Hoc Analysis では 1 ページに最大 50,000 行表示されます。データはまだ Analysis Workspace 内に存在しているので、1 ページあたりの行数は単純にデフォルトの 10 行になることに注意してください。 </li> 
     <li id="li_A8B8890149334032A56D8D1C0F8691EA"><b>アドバンス検索：</b>複数の同時検索オプションはサポートされませんが、単一の検索オプション（<span class="wintitle">次の単語のすべて</span>、<span class="wintitle">完全に一致</span>、<span class="wintitle">次の単語のいずれか</span>、<span class="wintitle">次の単語をどれも使用しない</span>、など）は Analysis Workspace に変換されます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：チャートやグラフはどのように変換されますか。</b> </p> </td> 
   <td colname="col2"> <p>回答：Analysis Workspace ではチャートやグラフはビジュアライゼーションと呼ばれることに注意してください。 </p> 
    <ul id="ul_597F5AB826EF434295D0CABD0313CAD5"> 
     <li id="li_AFB2805418034721A9519D999128C0A8"><b>設定</b>：Analysis Workspace では、項目数や棒グラフ数といったビジュアライゼーション設定はサポートされません。 </li> 
     <li id="li_D5C7EA8815344EDB8585CBB8E1AF583E"><b>円グラフ</b>：<a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/donut.html" format="html" scope="external">ドーナツグラフ</a>ビジュアライゼーションとしてエクスポートされます。Analysis Workspace のこのビジュアライゼーションでは、分割数の上限は 19 分割になっています。 </li> 
     <li id="li_91659FBFD77C4B3393D78447D658B7B4"><b>バブルチャート</b>：<a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/scatterplot.html" format="html" scope="external">散布図</a>ビジュアライゼーションとしてエクスポートされます。散布図ではデフォルトで、最初の指標が x 軸に、2 番目の指標が y 軸にそれぞれ描画されます。指標が 1 つしかない場合、バブルチャートは折れ線グラフビジュアライゼーションに変換されます。 </li> 
     <li id="li_FA05085FFB1747EBAF63616AC2B8D59C"><b>ヒストグラム</b>：Analysis Workspace と Ad Hoc Analysis では、サポートされるグループ化ロジックが異なっています。このため、ヒストグラムは<a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/bar.html" format="html" scope="external">棒グラフ</a>ビジュアライゼーションに変換されます。 </li> 
     <li id="li_959499D20796459CA0F6BBC8F0A8D808"><b>散布図</b>：Analysis Workspace にエクスポートされたプロジェクトでは、Y 軸が最初の列に設定され、X 軸が 2 番目の列、直径が 3 番目の列になります。 </li> 
     <li id="li_14E06D7A5106405A89A07B44FFD9A92D"><b>フォールアウトの表</b>：フォールスルーまたはフォールアウトの表を表示するには、チェックポイントを右クリックして分類オプションを選択します。 </li> 
     <li id="li_240F43C386F04111A7632A8FCA37832C"><b>フォールアウトレポートレベルの日付範囲</b>：カスタマイズされたレポートの日付範囲は、フォールアウトビジュアライゼーションに適用されていません。 </li> 
     <li id="li_1FF5B3FD9E424E7190AF03FD4DD9D654"><b>フローレポート</b>：日付範囲やセグメント化を維持するため、フローは個別のパネルに移動されます。 </li> 
     <li id="li_BE8F8F6EC2EA49E18EF52539BC1700E0"><b>コンバージョンファネル</b>：これは Analysis Workspace ではサポートされないので、フリーフォームテーブルに変換されます。コンバージョンファネルの代わりとしてお勧めなのは、フォールアウトビジュアライゼーションですが、これは若干異なる動作を示します。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：セグメントはどのように変換されますか。</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_15D5B17461E2402DB07DF8B0A10AAC37"> 
     <li id="li_CF9C3D235A664B15B21D9F89DC5EF7D3">セグメントは変換後のプロジェクトの内部（非公開）になります。以下に示すように、それらを公開することができます。 <p><img placement="inline"  src="assets/internal_segment.png" id="image_5942392F18E845A5B41C3DED59374E89" width="300px" /> </p> </li> 
     <li id="li_AE61DAEC5C0047349DD192EFEEDB0BF9">Ad Hoc Analysis のワークスペースレベルのセグメントは、Analysis Workspace のプロジェクト／ワークスペースレベルに適用されます。 </li> 
     <li id="li_B1559E2C18724FE189AF87D0BEF16811">Ad Hoc Analysis のレポートレベルのセグメントは、Analysis Workspace のテーブル列レベルに適用されます。 </li> 
     <li id="li_0E6DF6D44EA448A4A212BA2BB8E342CF">Ad Hoc Analysis の表のセグメントは、Analysis Workspace の列レベルに適用されます。 </li> 
    </ul> <p>セグメントを編集するには、<a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/" format="https" scope="external">セグメントビルダー</a>を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：日付範囲はどのように変換されますか。</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A24AB597F3CE4847AF00D49A9A72A395"> 
     <li id="li_24FD18AF64114445939C4FBC03F2D406">日付範囲「最近の X 日間」の場合、Ad Hoc Analysis では今日が<i>除外されます</i>が、Analysis Workspace では今日が<i>含められます</i>。このため、「最近の 90 日間」のような日付範囲は、ツール間で厳密に一致しない場合があります。Analysis Workspace で同じ期間を取得するには、カスタム日付範囲を使用してください。 </li> 
     <li id="li_AA4390470C494748B4B12030B1226720">Ad Hoc Analysis のワークスペースレベルの日付範囲は、Analysis Workspace のプロジェクト／ワークスペースレベルに適用されます。 </li> 
     <li id="li_B8F0CDD413154856A315D087FEC4D418">Ad Hoc Analysis のレポートレベルの日付範囲は、Analysis Workspace のテーブル列レベルに適用されます。 </li> 
    </ul> <p>カスタム日付範囲を編集するには、<span class="uicontrol">Analytics</span>／<span class="uicontrol">コンポーネント</span>／<span class="uicontrol">日付範囲</span>を選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：計算指標はどのように変換されますか。</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_ADA380D5D09B4223AAE4853D4C64F679"> 
     <li id="li_010572F793F54680ABE64117DAB7E800">計算指標はエクスポートされたプロジェクトの内部（非公開）になります。それらを公開するには、指標を右クリックして<span class="uicontrol">公開する</span>をクリックします。 <p><img placement="inline"  src="assets/calc_metric_internal.png" id="image_EA19BA55B161499CBDB9275A5C94BA90" width="200px" /> </p> </li> 
     <li id="li_930546EC8FEB432C8810FAF93556FC9A">すべてのタイプの計算指標がエクスポート対象としてサポートされています。 </li> 
     <li id="li_DFF7C6F8BB2344928D49194DA0F6EC38"><b>配分タイプ</b>：Analysis Workspace では計算指標の配分タイプは明示的に表示されませんが、エクスポート時には、Ad Hoc Analysis に存在していた配分タイプが作成され、そのタイプへのマッチングがおこなわれます。 </li> 
    </ul> <p>配分タイプを編集するには、編集（鉛筆）アイコンをクリックして<a href="https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/" format="https" scope="external">計算指標ビルダー</a>を開きます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：Ad Hoc Analysis のグローバルデータ設定は変換後のプロジェクトにどのように適用されますか。</b> </p> </td> 
   <td colname="col2"> <p>グローバルデータ設定を使用する場合、同じプロジェクトを 2 回エクスポートしたときに両者の動作が異なることがあります。 </p> 
    <ul id="ul_E3827883DD8045FAAB359D7E85E3EEFA"> 
     <li id="li_1056CA4813C44638BEB070228AE6914C"><b>繰り返しインスタンスのカウント：</b>エクスポート時に適用されていた設定が、Analysis Workspace 内のエクスポート後のプロジェクトに適用されます。 </li> 
     <li id="li_D5405E2862CF434CA82AA9DE000F4BBC"><b>データソース：</b> Analysis Workspace ではデータソースも含め、Analytics のすべてのデータが表示されます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：Ad Hoc Analysis プロジェクトのスケジュールが作成されていた場合、そのスケジュールは Analysis Workspace に変換されますか。</b> </p> </td> 
   <td colname="col2"> <p>スケジュールは一切変換されません。Analysis Workspace でスケジュールを作成するプロジェクトを開き、<span class="uicontrol">共有</span>／<span class="uicontrol">ファイルをスケジュールに従って送信</span>を選択して新しいスケジュールをセットアップします。Ad Hoc Analysis のスケジュールされたプロジェクトを忘れずにキャンセルしてください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>質問：2 つのツールの間で何か名前の違いはありますか。</b> </p> </td> 
   <td colname="col2"> <p>回答：はい。Analysis Workspace のドキュメントにある<a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/adhocanalysis_vs_analysisworkspace.html" format="html" scope="external">主な用語の比較</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

