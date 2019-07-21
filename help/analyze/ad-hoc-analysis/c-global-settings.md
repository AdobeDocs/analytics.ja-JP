---
description: グローバルな動作設定を行います。例えば、自動保存の設定、グラフと表の設定、フォントとロケールの指定などを行うことができます。
seo-description: グローバルな動作設定を行います。例えば、自動保存の設定、グラフと表の設定、フォントとロケールの指定などを行うことができます。
seo-title: 設定
title: 設定
uuid: 34444052-479b-4923- b379- a03ca614bf3e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 設定

グローバルな動作設定を行います。例えば、自動保存の設定、グラフと表の設定、フォントとロケールの指定などを行うことができます。

## 設定 {#concept_D21E3D6F13EA4F97913F60C243B72173}

グローバルな動作設定を行います。例えば、自動保存の設定、グラフと表の設定、フォントとロケールの指定などを行うことができます。

**[!UICONTROL ツール]** / **[!UICONTROL 設定]** をクリックして、グローバル設定にアクセス します。

## 「一般的な設定」タブの定義{#reference_EADAF83466994F89BCC6B0F49A9A53DB}

データソース、プロジェクト保存、グラフ、表に関する動作設定を行います。

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>フィールド </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> データ設定 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">繰り返しインスタンスをカウント</span>：インスタンスがレポート内でカウントされるかどうかを指定します。つまり、同じ変数に対して複数の連続する値が存在する場合、それらの値を変数の 1 つのインスタンスか複数のインスタンスのどちらかとしてカウントできます。 </p> <p>例えば、ページリロードの繰り返し（1 回の訪問で Web サイト上のページがリロードまたは更新される回数）を確認できます。このオプションでは、同じページでの複数のヒットを 1 回としてカウントするか、複数のページ表示回数としてカウントするかを指定できます。 </p> <p> <span class="uicontrol"><span class="keyword">Ad Hoc</span></span>：<span class="keyword">ad hoc</span> をレポートの唯一のデータソースとして指定します。このデータは、Web ページによって生成されたイメージ要求が基になります。 </p> <p> <span class="uicontrol"><span class="keyword">データソース</span></span>：他のアドビのソースまたはカスタムのデータソースからアップロードされたデータを使用するかどうかを指定します。このデータは、<span class="keyword">Experience Cloud</span> の製品で使用可能になります。詳しくは、<a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html" scope="external" format="html">Data Sources</a> を参照してください。 </p> <p> <span class="uicontrol">両方</span>：（デフォルト）<span class="keyword">ad hoc analysis</span> および他のデータソースからのデータを使用します。 </p> <p>注意：これらのオプションを変更すると、<span class="keyword">ad hoc analysis</span> と <span class="keyword">Reports and Analytics</span> の間でレポートの相違が起こる可能性があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 自動保存設定 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">自動保存有効</span>：自動保存機能を有効にします。 </p> <p> <span class="uicontrol">プロジェクトの自動保存頻度</span>：自動保存の時間間隔を調整できます。プロジェクトの自動保存は、ad hoc がクラッシュした場合にのみ作成されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> グラフ設定 </p> </td> 
   <td colname="col2"> <p><b>デフォルトでグラフを折りたたむ</b>：レポートを表示するときに最上部のセクションにグラフを表示しない場合には、このボタンをクリックします。このオプションをオンにしてレポートを表示した場合でも、グラフは手動で展開できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 表の設定 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">行番号の表示</span>：レポートの表に行番号を表示するかどうかを切り替えます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 「ランク」タブの定義{#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

列でのデータの表示方法や、トラフィックレポートとコンバージョンレポートのデフォルトの指標を設定します。

<!-- 

r_dsc_ranked_tab.xml

 -->

| フィールド | 定義 |
|--- |--- |
| コラム設定 | 表でのセルデータやグラフでの棒グラフの表示方法を設定します。 |
| デフォルト指標を選択 | すべてのレポートで使用できる指標のほかに、トラフィックレポートおよびコンバージョンレポートで使用するデフォルト指標を選択します。レポート固有のデフォルトを含める：表示のカスタマイズ時にデフォルト指標を含めるかどうかを指定します。 |

## 「サイト分析」タブの定義{#reference_9DD37C8EF718409E990E149596282FF8}

サイト分析レポートの指標やその他のグラフ設定を行います。

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| フィールド | 定義 |
|--- |--- |
| 指標 | シリンダーの幅およびシリンダーの高さで表す指標を選択します。色で表示する指標を指定し、その指標で低い値および高い値を示す色を指定します。X 軸と Y 軸の指標を指定したり、レポートのポップアップテキストに表示させるその他の指標を追加したりできます。また、選択した指標の表示を逆にすることもできます。 |
| 一般およびアラート | レポートの一部のグラフ要素を有効または無効にします。シリンダーで表されたページに関連する指標が特定の値を超えると、レポートにアラートが表示されるように設定できます。 |

## 「フォントとロケール」タブの定義{#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

言語の地域設定とデフォルトフォントを指定します。フォントとロケールの変更を有効にするには、再起動する必要があります。

<!-- 

r_dsc_font_locale.xml

 -->

| フィールド | 定義 |
|--- |--- |
| ロケールを選択 | ユーザーインターフェイスに表示する言語を指定できます。 |
| フォントを選択 | 表示フォントを指定できます。 |