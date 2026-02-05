---
description: Analysis Workspace でのデータ異常値検出について説明します。
title: 異常値検出の概要
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: ht
source-wordcount: '1292'
ht-degree: 100%

---

# 異常値検出の概要

Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。貢献度分析は、異常値検出と連携して、異常値の原因となった要素を特定するのに役立ちます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [異常値検出](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Adobe Analytics Select および Adobe Analytics Foundation をご利用のお客様は、Workspace で&#x200B;*毎日の精度*&#x200B;の異常値検出のみにアクセスできます。詳しくは、[異常値検出と貢献度分析の権限](#anomaly-detection-and-contribution-analysis-entitlements)を参照してください。

## 異常値の検出

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出により、「ノイズ」から「真のシグナル」を分離し、これらのシグナルまたは異常値の潜在的な要因を特定できます。つまり、変則性の検出を使用すると、重要な統計変動と重要でない統計変動を識別できます。さらに、信頼性の高い指標（KPI）予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上高の低い注文数のスパイク
* 体験版登録数のスパイクまたは下落
* ランディングページビュー数の下落
* ビデオバッファーイベント数のスパイク
* 低ビデオビットレートのスパイク

異常値検出と貢献度分析の双方が、[Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) の主要ワークフローになりました。毎日の異常値に対して貢献度分析を実行し、その結果を Analysis Workspace プロジェクトに埋め込むことができます。

Analysis Workspace の異常値検出アルゴリズムには、次の機能が含まれます

* 既存の日単位の精度に加えて、時間単位、週単位、月単位の精度のサポート。
* 季節性（「Black Friday」など）や休日の認識。

## 貢献度分析

貢献度分析は、データ内の非表示パターンを発見して統計的な異常値を明らかにし、次の項目の背後にある相関関係を特定します。

* 予期しない顧客のアクション、
* 範囲外の値、
* 突然のスパイクや下落

収束するオーディエンスセグメント全体の選択された指標の相関関係を特定します。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [貢献度分析](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


何かが発生しました。なぜですか？異常値検出レポートが、注文の指標で普通でないスパイクを示しています。何が異常だったのでしょうか？誰がどのキャンペーンやリファラルに対応しているのでしょうか？何かがバイラルになったのでしょうか？この異常値に貢献した特定の要因は何でしょうか。そしておそらく最も重要なこととして、どうしたら顧客に関する重要な情報をつかむことができ、このパフォーマンスを繰り返すことができるのでしょうか（または、指標の急激な下降やネガティブな指標の急増が発生した場合、将来、どうすれば避けることができるでしょうか。）

貢献度分析は、データを即座に評価して、異常値が発生した原因を知るのに役立ちます。これまで数週間かかっていた、異常値に対する貢献の分類を数秒でおこない、オーディエンスセグメントのパターンを提供して、顧客インタラクションの成功パターンをプランすることを支援します。貢献度分析を戦略的に使用することで、意味のある関連性を特定および把握できます。次に、これらの関連性を戦略的に使用して新しいオーディエンスセグメントを開発したり、戦術的に使用してアラートをトリガーする範囲外のアクティビティや不正なアクティビティを特定したりすることができます。

[異常値検出](#anomaly-detection)は、選択した指標やオーディエンスセグメントの範囲で、データのスパイクや極端な統計的下降を特定します。異常値検出では、トレーニング期間に基づいて履歴標準を設定し、特定のイベントに相関する極端なオフセットをプロットします。異常検出では、正の注文指標の急上昇、負のバウンス指標の上昇、またはその両方の下降をレポートし、統計的に関連するデータポイントを取得して、貢献度分析で評価できます。統計的な異常値を特定すると、貢献度分析を使用して、すべての異常なデータポイントをまたいでドリルダウンして、関連するマーケティング変数とキャンペーン変数を評価できます。高度なアルゴリズムと機械学習プロセスを実行して、大幅なスパイクまたは下落の原因となった関連性を評価します。これらの計算がインタラクティブなビジュアライゼーションで表示され、なぜ異常が起こったのかや、どう対処すべきかを知るのに役立ちます。

貢献度分析は、異常が発生した理由を説明するナラティブを作成するのに役立ちます。また、関連する指標を取得し、オーディエンスのインタラクションの全体的な理由や顧客の興味のトレンドを示す隠れたポイントを特定することで、異常値への対応方法も導きます。異常値には、2,000 艘のカヤックといった注文ミスなど、簡単に確認や修正をおこなえるものがあります。 一方、特定のターゲットキャンペーンにのみ反応する地域で、一定期間にわたって新たなトレンドが見られるなど、異常値は複雑な場合もあります。様々なディメンションの指標とその関連性での貢献項目をつなぎ合わせることで、オーディエンスのインタラクションの全体像を把握し、異常なデータポイントのコンテキストを提供するのに役立ちます。

使用例を次に示します。

* 製品需要の変化を監視することで、リマーケティングの可能性を特定する。
* 特定のオーディエンスの興味に対応することで、顧客体験を強化する。
* 範囲外レポートで不正注文を早期に識別する。
* 大量のアクセスとダウンロード数を識別して、企業スパイから自社を守る。
* 欠落している JavaScript タグのレポートなどの操作を監視します。

異常値貢献度分析をスタートさせてしばらくすると、貢献度の高いトップアイテムが合計発生数と貢献度の値の項目の割合で並べられた貢献度の概要レポートが生成されます。正規化された貢献度スコアを使用すると、ディメンション間での比較、対象、関連度の調整ができます。

## 貢献度分析トークン

貢献度分析の使用権限を持つすべてのお客様は、Analysis Workspace で 1 か月あたりに限られた回数、完全な貢献度分析を実行できます。貢献度分析では、ポイント製品（SiteCatalyst 15）のお客様、Analytics Foundation のお客様、Analytics Select のお客様は&#x200B;**除外**&#x200B;されます。これらのお客様には、貢献度分析の使用権限がありません。

会社ごとの実行回数は、会社が購入した Adobe Analytics 製品に基づいて付与される毎月のトークンによって制限されます。会社ごとの実行回数には、トークンの誤用を防ぐために貢献度分析へのアクセスを制限する機能が含まれます。

## よくある質問

| 質問 | 回答 |
| --- | --- |
| アドビがトークンを導入した理由 | 貢献度分析は、Adobe Analytics の最も重要な機能の 1 つになりました。一部の Analytics 製品のようにディメンション数を 3 つに制限するのではなく、ごく限られた回数でも 1 か月に何度か完全な機能を実行できるようにすることで、制限のない完全な貢献度分析のメリットを実感していただけるものと考えています。 |
| 貢献度分析のトークンはどのように機能しますか？プロジェクトに既存の貢献度分析を実装するときもトークンが必要ですか。それとも、新しい貢献度分析を実行するときにのみ、トークンが必要ですか。 | 各ログイン会社（各ユーザーではなく）は、1 か月あたり定められた数のトークンを入手します。これらのトークンを使用して、Analysis Workspace 内で「完全な」貢献度分析を実行できます。新しい貢献度分析を生成するたびに、1 トークンをお支払いいただきます。事前実行済みの貢献度分析を含むプロジェクトを読み込む場合、トークンは発生しません。 |
| トークンを切らしていますが、さらに貢献度分析を実行したい場合はどうしますか？ | 別の Adobe Analytics の製品にアップグレードできます。例えば、Standard（2 トークン/月）から Ultimate（20 トークン/月）にアップグレードできます。トークンを追加購入することはできません。既存のパッケージフレームワーク内でアップグレードする必要があります。 |
| 貢献度分析へのアクセスを制限するには、どのようにしますか。 | デフォルトでは、管理者のみが貢献度分析を実行するアクセス権を持っています。ただし、管理者は [Adobe Admin Console](/help/admin/admin-console/home.md) に権限グループを作成することで、他のユーザーにアクセス権を付与できます。貢献度分析を使用する正当な理由があり、かつアクセス権を悪用しない信用できるユーザーに対してのみ、貢献度分析の使用権限を付与します。この権限は、[!UICONTROL レポートスイートツール]の下で[!UICONTROL 貢献度分析]と呼ばれます。[詳細情報](/help/admin/admin-console/permissions/report-suite-tools.md) |
| 1 か月あたり使用可能なトークン数と、当月に使用したトークン数は、どうすればわかりますか？ | [!UICONTROL 管理者] ／ [!UICONTROL すべての管理者] ／ [!UICONTROL 会社設定ホーム] ／ [!UICONTROL 機能アクセスレベルを表示]に移動します。以下の下を見てください。<ul><li>貢献度分析：月使用トークンの数</li><li>貢献度分析：今月使用された使用トークンの数</li></ul> |

## 異常値検出と貢献度分析の権限

Analysis Workspace における異常値検出と貢献度分析の詳細な権限のリストを以下に示します。

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics の使用権限 </th> 
   <th colname="col2" class="entry"> 異常値検出 </th> 
   <th colname="col3" class="entry"> 貢献度分析 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>毎日の精度のみ </p> </td> 
   <td colname="col3" colsep="1"> <p>トークンなし </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&amp;mv=other"  >Select</a> </p> </td> 
   <td colname="col2"> <p>毎日の精度のみ </p> </td> 
   <td colname="col3"> <p>トークンなし </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 か月あたり 10 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 か月あたり 20 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Predictive Workbench アドオン </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>無制限のトークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 か月あたり 2 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（360、アトリビューション） </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 か月あたり 2 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（Complete、<a href="https://business.adobe.com/jp/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>） </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>無制限のトークン </p> </td> 
  </tr> 
 </tbody> 
</table>
