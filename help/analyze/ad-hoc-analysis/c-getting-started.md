---
description: Ad Hoc Analysis の概要を説明します。
title: はじめに
uuid: 6a698e18-4e62-405e-b020-b973c9c4008b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Ad Hoc Analysis の概要 {#concept_48936BA28FAE42DB81F1B2CD4726EB17}

>[!I重要]
>2018 年 8 月 6 日、アドビは Ad Hoc Analysis のサポート終了の意向を表明しました。サポート終了日については確定次第お知らせします。サポート終了の予定や詳細については [https://adobe.ly/discoverworkspace](https://adobe.ly/discoverworkspace) を参照してください。

Webサイトの高度な分析を即時に実行できます。 複数のレポートを同時に表示し、複数のディメンションにセグメントを適用できます。 ミクロ的観点とマクロ的観点の両方からデータを分析し、重要なビジネス指標に対する表示の影響を分析することができます。

これらの機能を使用すると、サイトトラフィック、訪問者人口統計、売上高、製品の動きに関する質問に答えることができます。 その後、データをフィルタ、並べ替え、セグメント化して、正確な質問に対する答えを見つけることができます。 結果はほとんど瞬時に返されるので、複数の要素の組み合わせによる効果を迅速に分析できます。

<table id="table_C9C0444687FC418580F996E1D2ADB61A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用開始までの流れ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1. Adobe <span class="keyword">Analytics</span> にログインする。 </p> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com"  >marketing.adobe.com</a> にアクセスして、Adobe Analytics の資格情報を使用してログインします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2. Ad Hoc Analysis を起動する。 </p> </td> 
   <td colname="col2"><span class="uicontrol">Adobe Analytics</span>／<span class="uicontrol">ツール</span>／<span class="uicontrol">Ad Hoc Analysis</span> をクリックして、「<span class="uicontrol">Ad Hoc Analysis を起動</span>」ボタンをクリックします。 <p> <p>注意：このページに「<b>Ad Hoc Analysis を起動</b>」ボタンが表示されない場合は、管理者が管理ツールの「<i>Ad Hoc Analysis ライセンスユーザー</i>」グループにユーザーを追加していることを確認してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3. プロジェクトを作成する。 </p> </td> 
   <td colname="col2"> <p>スタートアップページで、レポートスイートを選択して「<span class="uicontrol">プロジェクトの作成</span>」をクリックします。 </p> <p><a href="/help/analyze/ad-hoc-analysis/c-getting-started.md"   >プロジェクトと Workspaces</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4.レポートを開きます。 </p> </td> 
   <td colname="col2"> <p>標準のCloudレポートメニューを使用してレポートを検索します。 また、テンプレートを選択することもできます。 </p> <p>「レポートテ <a href="/help/analyze/ad-hoc-analysis/c-getting-started.md"   > ンプレート</a>」を参照。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5.レポートを設定します。 </p> </td> 
   <td colname="col2"> <p>次のようなタスクを実行して、レポートを設定します。 </p> 
    <ul id="ul_0D2E8C614F2A4899A376BCEECEA374C6"> 
     <li id="li_FA925D52A8FD4DFAB0C88B797B24E72B"> セグメントを作成してデータをより深く掘り下げる </li> 
     <li id="li_5E91632551D2473BA8BD0637CDC1A9F6"> 表ビルダーへの指標、ディメンションおよびセグメ <a href="/help/analyze/ad-hoc-analysis/c-tablebuilder.md"   > ントの追加</a> </li> 
     <li id="li_019316C9A94B4A8C8A77D07C04E50278"><a href="/help/analyze/ad-hoc-analysis/c-dates.md"   >日付範囲</a>の設定 </li> 
     <li id="li_2B33B325D5EE420AB412B73AD1D231C5"> <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > レポート配信のスケジュール</a>を設定する </li> 
    </ul> <p>このヘルプシステムで検索して、必要なヘルプを参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 必要システム構成 {#concept_6691331B45174290BD9B839806A9B52D}

レポートはほとんどの Web ブラウザーで適切に機能しますが、レポートの表示と機能に最適なシステム要件があります。

<!-- 

c_sys_reqs.xml

 -->

>[!NOTE]2018 年 7 月から、Ad Hoc Analysis では Java 8 以降のみがサポートされます。お客様が 2018 年 7 月のメンテナンスリリース以降に Java 7 で Ad Hoc Analysis を実行することを選択した場合、アドビはお客様の Ad Hoc Analysis 実装をサポートしません。

* OpenGL 2.0をサポートするビデオカード
* Cookie:必須
* オペレーティングシステム：WindowsおよびMac OS。
* Macromedia Flash Player:バージョン6以降
* 画面の解像度：800 x 600（1024 x 768を推奨）
* 色深度：16ビット以上
* JavaScript:有効
* Javaバージョン：Java 1.7以降（上記の「注意」を参照）

   正しいバージョンのJavaがインストールされていない場合は、インストールされます。 互換性のないバージョンのJavaがインストールされている場合、Ad Hoc分析はアップデートをダウンロードし、インストールするように求めます。

## Javaのアップグレード手順 {#section_E4C0C6492FF24636A0FF71A59331111D}

2018 年 7 月から、Ad Hoc Analysis では Java 8 以降のみがサポートされます。お客様が 2018 年 7 月のメンテナンスリリース以降に Java 7 で Ad Hoc Analysis を実行することを選択した場合、アドビはお客様の Ad Hoc Analysis 実装をサポートしません。

アドビの.jarファイルは、1.7.0_76より前のJavaバージョンではサポートされない、安全な256ビット暗号化を使用して署名されています。 この256ビット証明書を使用すると、セキュリティが強化されます。

まだ Java 7 がインストールされている場合、2018 年 7 月のメンテナンスリリースの前にアップグレードする必要があります。その方法を次に示します。

* コンピューターにプログラムをインストールできる場合：

   1. https://www.java.com に移動します。
   1. クリック **[!UICONTROL Free Java Download]**.
   1. クリック **[!UICONTROL Agree and Start Free Download]**.
   1. お使いのオペレーティングシステムに固有の最新のJavaバージョンをインストールします。

* コンピューターに **プログラム** をインストールできない場合：

   1. IT部門と協力して、最新バージョンのJavaをインストールします。

## Ad Hoc Analysis の起動 {#concept_B1CE3C1E6D1A4311B9835BEB69812E55}

<!-- 

c_login.xml

 -->

[!DNL Experience Cloud] または URL からログインできます。Reports &amp; Analyticsからログインすると、自動的にログインします。 URLを使用してログインする必要があるのは、リンクやお気に入りメニューなど、別の場所からアドホック分析のURLにアクセスする場合のみです。

## Experience Cloud からのログイン {#task_128ED319F3AE49ED886EA3DFA8D0987F}

[!DNL Experience Cloud] からログインする手順を説明します。

<!-- 

t_login_suite.xml

 -->

1. ブラウザーで、[!DNL marketing.adobe.com] に移動します。
1. Type your company name, your username, and your password. Then click **[!UICONTROL Sign In]**.
1. Click **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Ad Hoc Analysis]**.

   このページに「**Ad Hoc Analysis を起動**」ボタンが表示されない場合は、管理者が管理ツールの「*Ad Hoc Analysis ライセンスユーザー*」グループにユーザーを追加していることを確認してください。
1. クリック **[!UICONTROL Launch Ad Hoc Analysis]**.
1. [!DNL discover.jnlp] ファイルをローカルに保存します。

   この保存したファイルは、Ad Hoc Analysis を起動する際にいつでも実行できます。

## プロジェクトとワークスペース {#concept_FAE346335B0347A192C6C806C775D72B}

プロジェクトは、レポートスイートや日付範囲など、読み込まれるデータのセットを定義します。 プロジェクトは、任意の数のレポートと、そのすべての指標、設定、ディメンション、セグメントで構成されます。 新しいプロジェクトを開始したり、保存されたプロジェクトを読み込んだり、自動的に保存されたプロジェクトを読み込んだりできます。

<!-- 

c_projects.xml

 -->

レポートをワークスペースにグループ化 *します*。 1つのプロジェクトに複数のワークスペースを含めたり、1つのワークスペースに複数のレポートを含めたりできます。 これらの項目間の関係は、入れ子になったものとして理解するのが最適です。

![](assets/project_workspace.png)

一度に開くことができるプロジェクトは1つだけです。 ただし、1つのプロジェクトで複数のワークスペースを開くことができます。 各ワークスペースで、複数のレポートを開くことができます。

新しいプロジェクトのデフォルトの日付範囲はで [!UICONTROL Last 90 Days]す。

## プロジェクトの開始 {#task_918A4539134E4E62B00486DCB8D3D403}

プロジェクトを開始する手順を説明します。

<!-- 

t_project_start.xml

 -->

1. ログインします。
1. Open a saved project or click **[!UICONTROL Create Project]**.
1. レポートを検索して選択するか、テンプレートを選択します。

## 最近保存したワークスペースを開く {#task_DE4A54180BC24E9DAEC98E2171DC6B40}

最近保存したワークスペースを開く手順を説明します。

<!-- 

t_recent_workspace.xml

 -->

1. クリック **[!UICONTROL File]** > **[!UICONTROL Recent Workspace]**.

   最近使用したワークスペースは5つまで開くことができます。 セッションを終了すると、最近使用したワークスペースは使用できなくなります。

## プロジェクトの共有 {#task_5911780D90164F3A8A677C8BC719750D}

共有プロジェクトは、会社のすべての Ad Hoc Analysis ユーザーが利用できます。

<!-- 

t_share_projects.xml

 -->

1. Go to **[!UICONTROL File]** > **[!UICONTROL Save As]**.
1. ドロッ **[!UICONTROL Shared Projects]** プダウンか **[!UICONTROL Save in:]** らを選択します。

   ![](assets/shared_projects.png)

1. Click **[!UICONTROL Save]** to save the project.

   共有プロジェクトは、//で **[!UICONTROL File]** 開くこ **[!UICONTROL Open]** とができま **[!UICONTROL Shared Projects]**&#x200B;す。

   >[!NOTE]
   >
   >1 つまたは複数のプロジェクトを選択することで、プロジェクトを共有するのと同じダイアログボックスで自分の共有プロジェクトを削除できます。

## ワークスペース名の変更 {#task_0DB177DD6DB54B7F9FE60A0B3FC7CFC3}

ワークスペース名を変更する手順を説明します。

<!-- 

t_rename_workspace.xml

 -->

1. ワークスペース名を右クリックします。
1. Choose **[!UICONTROL Rename Workspace]**.
1. 名前を入力し、「**[!UICONTROL OK]**」をクリックします。

## ローカルプロジェクトを開く {#task_1B3EF63A80C74776B24B99D80EAC74AC}

プロジェクトのローカルコピーを開く手順を説明します。

<!-- 

t_open_local_project.xml

 -->

1. クリック **[!UICONTROL File]** > **[!UICONTROL Open Local Copy]**.
1. Navigate to the local [!DNL .dproj] file, then click **[!UICONTROL Open]**.

## レポートテンプレート {#concept_370F674C5B4C45368731AA801C5A45F8}

テンプレートは、実行する分析の種類の開始点です。 テンプレートは、ランクレポートやフォールアウトレポートなど、空白のキャンバスにすることができます。 また、テンプレートは、デフォルトの指標とディメンションを開始とするレポートです。

<!-- 

c_templates.xml

 -->

You can access templates when creating a project ( **[!UICONTROL File]** > **[!UICONTROL New Project]**), or by adding a workspace or report.

| テンプレート | 説明 |
|--- |--- |
| ランク | テーブルを作成できる空白のキャンバスが表示されます。 例えば、ページレポートでは、トラフィックに基づいてサイト上の各ページがランク付けされ、詳細テーブルにページビュー数や売上高などの指標に関する割合と数値が表示されます。 |
| トレンド | レポート期間中の、選択した時間の精度（時間、日、週、月、四半期、年）におけるコンバージョンとイベントのトレンドを調べます。 |
| 合計 | 最終的な数字を示すエグゼクティブレベルのレポート。 合計売上高、ページ表示数、注文件数のデータが含まれます。 |
| フォールアウト | チェックポイント間のコンバージョン率とフォールアウト率を表示するファネルを作成できます。 例えば、購入プロセス中の訪問者のフォールアウトポイントを追跡できます。 |
| フロー | ページ、サイトセクション、サーバ間で最も一般的なパスを表示します。 |
| コンバージョンファネル | 特定の指標イベント間のコンバージョン率。 このレポートを使用して、売上を生み出すクリックスルー数と販売数を把握できます。 |
| サイト分析 | 指定したページやページ間を訪問者がどのように移動するかを表示する3次元のサイトパスツール。 |
| 仮想フォーカスグループ | 訪問からランダムに1回の訪問を受け取り、その訪問に関する大量のデータを表示します。 このレポートを使用して、フォーカスグループを訪問者の訪問者から作成できます。 |

## レポートを開く {#task_0AC455CDA198497AA546622FB05F300D}

レポートやテンプレートは、プロジェクトの作成時に、または既存のプロジェクト内から開くことができます。 テンプレートを使用して、レポートを最初から設定します。

<!-- 

t_reports_opening.xml

 -->

レポートを開く方法はいくつかあります。

* ページで、 [!UICONTROL New Report] レポートを検索するか、テンプレートを選択します。
* メニュー **[!UICONTROL Reports]** からをクリックし、レポートまたはレポートテンプレートを選択します。
* ディメンションからレポートを開始する：ディメンション名を右クリックし、/を選 **[!UICONTROL Run Report]** 択しま **`report name`**&#x200B;す。
