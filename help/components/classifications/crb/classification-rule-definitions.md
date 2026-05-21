---
description: 分類ルールビルダーのページ上のインターフェイス要素の定義です。
title: 分類ルール - 定義
feature: Classifications
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
TQID: https://experienceleague.adobe.com/8SDdKOvF-Mk9jQCb7YWXt0NCl0dspfscnHL02y1cxKM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 861
ht-degree: 57%

---

# 分類ルール定義（レガシー）

{{classification-rulebuilder-deprecation}}

分類ルールビルダーのページ上のインターフェイス要素の定義です。

## ルールページ

このページには、ルールセットのルールが表示されます。

![](assets/classification_rules_page.png)

**定義**

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>レポートスイートと変数の選択 </p> </td> 
   <td colname="col2"> <p><b>レポートスイート</b> </p> <p>ルールセットが適用されるレポートスイート。 </p> <p><b>変数</b> </p> <p>分類ルールセットの作成時に適用できる変数は1つだけです。 1つの変数に複数のルールセットを作成する場合は、各ルールセットを複数のレポートスイートに適用する必要があります。 </p> <p>注意：レポートスイートでは、アクセス権のある変数のみを使用できます。 変数は、その変数に対して 1 つ以上の分類が定義されている場合にのみ<span class="wintitle">新しいルールセット</span>パネルに表示されます。 </p> <p> 変数の分類を作成するには、<span class="uicontrol">管理者</span>／<span class="uicontrol">レポートスイート</span>／<span class="uicontrol">トラフィック</span>／<span class="uicontrol">トラフィック分類</span>（または<span class="uicontrol">コンバージョン</span>／<span class="uicontrol">コンバージョンの分類</span>）を使用します。 次に、変数を選択し、「<span class="uicontrol">分類の追加</span>」をクリックします。 </p> <p>管理ヘルプの<a href="/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md"  >トラフィック分類</a>および<a href="/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md"  >コンバージョンの分類</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> アクティブ化</span> </p> </td> 
   <td colname="col2"> <p>ルールを検証してアクティブ化します。 アクティブなルールは日次で処理され、通常は1か月さかのぼって分類データを調査します。 ルールは新しい値を自動的にチェックし、分類をアップロードします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 非アクティブ化</span> </p> </td> 
   <td colname="col2"> <p>ルールを編集およびテストできるように非アクティブ化します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートスイートと変数の設定 </p> </td> 
   <td colname="col2"> <p><span class="wintitle">利用可能なレポートスイート</span>が表示されます。このページでは、利用可能なレポートスイートから、すべてのルールセットで使用する 1 つ以上のレポートスイートを選択できます （このページは、<span class="wintitle">分類ルールビルダー</span>を最初に実行したときにも表示されます）。 </p> <p>この機能は、非常に多くの利用可能なレポートスイートが存在する場合に、レポートスイートのロード時間を短縮するのに役立ちます。 </p> <p>ここで選択したレポートスイートは、ルールの作成時に「<span class="uicontrol">スイートを追加</span>」をクリックすると、ルールレベルで利用できるようになります。 </p> <p>レポートスイートは、<span class="wintitle">管理ツール</span>で、変数に対して定義された分類がレポートスイートに 1 つ以上ある場合に<span class="term">のみ</span>使用可能になります。 <p>（この前提条件については、<a href="/help/components/classifications/crb/classification-rule-set.md"  >分類ルールセット</a>の<span class="term">変数</span>を参照してください。） </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ルールによって既存の値は上書きされます </p> </td> 
   <td colname="col2"> <p> （デフォルト設定）インポーター（SAINT）を介してアップロードされた分類を含む、既存の分類キーを常に上書きします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ルールによって未設定の値のみが上書きされます </p> </td> 
   <td colname="col2"> <p>空白（未設定）のセルのみを入力します。 既存の分類は変更されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ルックバックウィンドウ </p> </td> 
   <td colname="col2"> <p>ルールをアクティブ化および検証する場合、そのルールの影響を受けるキーの既存の分類を上書きするかどうかを指定できます （指定した期間内に <span class="keyword">Adobe Analytics</span> に渡された分類されたキーのみが影響を受けます）。 </p> <p><span class="term">のルックバックウィンドウ </span>を指定しない場合、ルールは約1か月（月の現在の日付に応じて）振り返られます。 このオプションを有効にしない限り、既存の分類は上書きされません。 </p> <p><b>開発センター</b>：パートナーは、<span class="wintitle">開発センター</span>で分類ルールを作成できます。 これらのルールは、顧客が統合をアクティブ化すると表示されます。 <span class="wintitle">開発センター</span>で「<span class="uicontrol">以降を上書き</span>」オプションを使用すると、パートナーは、顧客が統合をアクティブ化または編集するときに上書き値を決定できるかどうかを指定できます。 </p> <p>ルール処理について詳しくは、<a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >ルールの処理方法</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >ルールを追加</a> </td> 
   <td colname="col2"> <p>ルールをルールセットに追加します。 </p> <p>注意：1 つの値がルールセット内で複数回一致する場合は、最後のルールを使用して値が分類されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">ドラフト</span> </td> 
   <td colname="col2"> ルールがドラフトモードであることを指定できます。 ドラフトステータスを使用すると、ルールを実行する前にルールをテストできます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">複製</span> </td> 
   <td colname="col2"> ルールセットを別の変数や異なるレポートスイートの同じ変数に適用できるように、ルールセットを複製（コピー）します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > テスト用ルールセット </a> </p> </td> 
   <td colname="col2"> <p>ルールセットの正当性をテストします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">一致条件</span> </td> 
   <td colname="col2"> ルールの条件を指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">分類アクション</span> </td> 
   <td colname="col2"> <p>一致する条件が発生したときに実行するアクションを指定します。 </p> <p>例えば、キャンペーン名を$2に設定し、トラッキングコードの位置2をキャンペーン名として識別します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>ルール番号。 </p> <p>詳しくは、<a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >のルールの処理方法</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">ルールタイプを選択</span> </td> 
   <td colname="col2"> <p>各ルールセットは、特定の変数に適用されます。 有効な選択項目は次のとおりです。 </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">次の語句で始まる </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">次の語句で終わる </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">次を含む </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >正規表現</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">一致条件を入力</span> </td> 
   <td colname="col2"> キーで探しているテキストパターン。 これらの条件には、検索語、文字、または正規表現を使用できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">分類を設定</span> </td> 
   <td colname="col2"> 一致条件が満たされた場合に設定する分類列。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">設定値</span> </td> 
   <td colname="col2"> 一致条件が満たされている場合に、選択した分類列に指定する値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フィルター </td> 
   <td colname="col2"> ルールを検索できます。 </td> 
  </tr> 
 </tbody> 
</table>

## 正規表現ページ {#section_C932A5469E774841B2229965A154163C}

正規表現は、[!UICONTROL 正規表現] ページで編集できます。

![](assets/regex_tracking_code.png)

**定義**

| 要素 | 説明 |
|---|---|
| サンプルキー | 使用するテスト文字列。 例えば、トラッキングコードの特定の文字から分類を作成できます。 特定の文字、単語、または文字のパターンを一致させることができます。 |
| 一致グループ | 正規表現がキャンペーン IDの文字にどのように対応するかを示します。これにより、キャンペーン ID内の位置を分類できます。 |
| 一致結果 | 正規表現と一致する文字列の部分を表示します。 |

分類ルール [&#128279;](/help/components/classifications/crb/classification-quickstart-rules.md)の正規表現を参照してください。

## テストページ {#section_EC926F97901C4E65901413F9683AA70A}

このページでは、セット内のルールをテストできます。

**定義**

| 要素 | 説明 |
|---|---|
| テストを実行 | ルールセットをテストする場合は、レポートのキーを使用して、ルールセットの影響を受ける方法を確認します。 |
| フィルター | [!UICONTROL 結果] パネルの値をフィルタリングします。 |
