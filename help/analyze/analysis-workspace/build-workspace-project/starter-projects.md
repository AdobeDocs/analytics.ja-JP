---
description: 'null'
title: テンプレート
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# テンプレート

## テンプレート {#topic_40932F09E18A467983AFBB29908E1CB8}

以下からプロジェクトを作成するかどうかを選択できます。

* 空白のプロジェクト（デフォルト）。手順については、[Analysis Workspace プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)を参照してください。
* 標準テンプレート。これらのテンプレートは、アドビによって作成され、標準で提供されます。
* カスタムテンプレート。これらのテンプレートは、「テンプレートとして保存」権限が与えられている場合に、管理者権限を持つユーザーまたは管理者以外のユーザーが作成できます（詳しくは、Admin Console ドキュメントの[製品権限の管理](https://helpx.adobe.com/jp/enterprise/using/manage-permissions-and-roles.html)を参照してください）。

![](assets/start_modal.png)

* [カスタムテンプレートの作成](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)
* [標準テンプレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)

## カスタムテンプレートの作成 {#create-custom-template}

管理者権限を持つユーザーは、作成した任意のプロジェクトをカスタムテンプレートに変換できます。その方法を次に示します。

1. そのプロジェクトを開きます。
1. **[!UICONTROL プロジェクト]**／**[!UICONTROL テンプレートとして保存]**&#x200B;に移動します。

   ![](assets/save_project_template.png)

   プロジェクトは、現在のプロジェクト名の下に、括弧に囲まれた単語（テンプレート）が続く名前で保存されます。管理者は、テンプレートを編集することで、この名前を変更できます。

   >[!NOTE]
   >
   >デフォルトでは、プロジェクトテンプレートは、組織の全員に表示されます。タグを適用することで、これを整理できます（タグおよび説明を編集するには、**[!UICONTROL プロジェクト]**／**[!UICONTROL プロジェクト情報および設定]**&#x200B;に移動します）。

### カスタムテンプレートで実行できるアクション

![](assets/custom_templates.png)

<table id="table_D7C7B0CA1EE64E108484C03426800EBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アクション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>テンプレートを編集 </p> </td> 
   <td colname="col2"> <p>管理者は、そのデータソースを変更したり、コンポーネント、ビジュアライゼーション、日付範囲などを変更したりすることで、テンプレートを編集できます。 </p> <p>カスタムテンプレートを編集するには、次のいずれかを実行します。 </p> 
    <ul id="ul_2B3A371F83334E14806385753A360903"> 
     <li id="li_EE75E0281B764BA9B56FF1DB1B12D2CC">Analysis Workspace でカスタムテンプレートのリストを表示し、カスタムテンプレートを選択して、「<span class="uicontrol">テンプレートを編集</span>」をクリックする。 </li> 
     <li id="li_4934DAAA46204990A295E22A97F81EDA">Analytics で、<span class="ignoretag"><span class="uicontrol">コンポーネント</span>／<span class="uicontrol">プロジェクト</span></span>に移動し、<span class="uicontrol">テンプレート</span>をフィルターして、編集するテンプレートの名前をクリックする。 </li> 
    </ul> <p> </p> <p>注意：テンプレートを編集した後、状況に応じて、「<span class="uicontrol">保存</span>」と「<span class="uicontrol">名前を付けて保存</span>」の 2 つのオプションがあります。その違いを次に示します。 
     <ul id="ul_87E2842C8AA442399585B1C6189F5E16"> 
      <li id="li_AB7B189729E14E40A0141ECE2A24C113"><b>保存</b>：すべてのユーザーのカスタムテンプレートを更新します。他のユーザーがこのカスタムテンプレートからプロジェクトを作成すると、加えた変更が表示されます。 </li> 
      <li id="li_C85B0B9873A3404D8B443BBD30B37CEB"><b>名前を付けて保存</b>：変更を加えたカスタムテンプレートのコピーを作成します。 </li> 
     </ul> </p> <p>（<span class="uicontrol">共有</span>／<span class="uicontrol">プロジェクトを共有</span>メニュー項目が無効になっている場合は、編集モードです。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テンプレートを検索 </p> </td> 
   <td colname="col2"> <p>カスタムテンプレートダイアログで、「<span class="uicontrol">テンプレートを検索</span>」をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テンプレートを並べ替え </p> </td> 
   <td colname="col2"> <p>テンプレートをアルファベット順、関連性順および作成日順で並べ替えることができます。 </p> <p>カスタムテンプレートダイアログで、「<span class="uicontrol">並べ替え</span>」をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テンプレートにタグを適用 </p> </td> 
   <td colname="col2"> <p>テンプレートを開いて、<span class="ignoretag"><span class="uicontrol">プロジェクト</span>／<span class="uicontrol">プロジェクト情報および設定</span></span>に移動します。「<span class="uicontrol">タグを追加</span>」をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テンプレートの説明を変更 </p> </td> 
   <td colname="col2"> <p>テンプレートを開いて、<span class="ignoretag"><span class="uicontrol">プロジェクト</span>／<span class="uicontrol">プロジェクト情報および設定</span></span>に移動します。説明をダブルクリックして編集します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 標準テンプレート{#concept_4FE900FEEC894E849CB6C6A0E0ADA524}

最初に Workspace を開くと、左側のパネルでテンプレートを使用できるようになります。Analysis Workspace のテンプレートは、一般的な使用例に対応しています。それらは、所属する部門ごとにグループ化され、選択したレポートスイートに応じて、異なるディメンション、セグメント、指標およびビジュアライゼーションで設定されます。

これらの事前設定されたテンプレートをそのまま、またはニーズに応じて変更して（例えば指標やビジュアライゼーションを追加または置き換えることで）使用して、新しい名前で保存できます。

[Analysis Workspace での標準テンプレート（YouTube）](https://www.youtube.com/watch?v=aRgYwPneVXg&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=6)（2:46）

以下に、利用可能なテンプレートと各テンプレートに関する質問について説明します。

### 広告

>[!IMPORTANT]
>
>広告テンプレートは、レポートスイートが Advertising Cloud で有効になっている場合にのみ使用できます。

* **検索エンジン**：このテンプレートは、広告の傾向、広告プラットフォーム、キーワード、アカウント、キャンペーンなどを分類します。

### コマース

* **Magento：マーケティングとコマース**：このテンプレートは、マーケティングチャネルアトリビューション別に e コマースコンバージョンを分類し、検索キーワード、ランディングページ、地理的な場所などによるインサイトを提供します。ビデオの概要については、[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw) を参照してください。

### メディア

* **オーディオ消費**：最も消費され、ユーザーを引き付けているのはどのコンテンツですか。
* **最新性 - 頻度 - ロイヤルティ**：常連読者は誰ですか。

### モバイル

>[!IMPORTANT]
>
>モバイルテンプレートは、レポートスイートがモバイルに対して有効になっている場合にのみ使用できます。

* **メッセージ：**&#x200B;アプリ内およびプッシュメッセージのパフォーマンスに重点を置いています。
* **ロケーション：**&#x200B;ロケーションデータを表示するマップを含みます。
* **主要指標：**&#x200B;アプリの主要指標の状況を把握します。
* **アプリ使用状況：**&#x200B;アプリのアプリユーザー数、起動数、初回起動数はいくつですか。また、セッションの長さの平均はどれくらいですか。
* **獲得：**&#x200B;モバイル獲得リンクがどのように実行されているかを確認します。
* **パフォーマンス：**&#x200B;どのようにアプリが実行され、ユーザーはどこに問題を抱えていますか。
* **リテンション：**&#x200B;常連ユーザーは誰で、何をしていますか。
* **ジャーニー：**&#x200B;アプリで目立つ使用パターンは何ですか。

### 小売

* **キャンペーンのパフォーマンス：**&#x200B;最も高い売上を促進しているのはどのキャンペーンですか。
* **製品：**&#x200B;どの製品が最も高いパフォーマンスを発揮していますか。

### Web

* **獲得：** Web サイトに最もトラフィックを呼び込んでいるのは何ですか。
* **コンテンツ消費：**&#x200B;サイトで人々が最も訪れている場所はどこですか。
* **リテンション：**&#x200B;サイトの常連ユーザーになる傾向があるのはどのタイプのユーザーですか。
* **テクノロジー：**&#x200B;人々がサイトにアクセスするのに使用しているのはどの技術ですか。

### People

> [!NOTE]人物テンプレートとそれに関連する人物指標は、[Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/ja_JP/mcdc/mcdc-people.html) の一部としてのみ使用可能です。

このテンプレートは、実訪問者指標の重複を排除したバージョンである人物指標に基づいています。人物指標は、消費者がブランドと関わる際にどのくらいの頻度で複数のデバイスを使用しているかを測定します。このテンプレートでは次の操作が可能です。

* 米国／カナダとそれ以外でデータをセグメント化する。現在、Device Co-op を使用できるのは北米のみです。
* 人物指標と実訪問者数指標を並べて比較する。
* 「圧縮率」（実訪問者に対して人物指標がどれくらい小さいかを計算する計算指標）を表示する。
* 顧客が使用するデバイスタイプの合計を比較する。
* 1 人あたりの平均使用デバイス数を表示する。
* 人物指標でセグメントのスタックを使用する方法を発見する。
* 環境での Experience Cloud ID の使用が、人物指標の効果をどのように高めているかを調べる。

