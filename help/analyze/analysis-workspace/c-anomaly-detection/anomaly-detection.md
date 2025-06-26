---
description: Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。
title: 異常値検出の概要
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 70%

---

# 異常値検出の概要

Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。貢献度分析は、異常値検出と連携して、異常値に貢献した項目の特定に役立ちます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ 異常値検出 ](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Adobe Analytics Select およびAdobe Analytics Foundationのお客様は、Workspaceでの *毎日の精度* 異常値検出にのみアクセスできます。 詳しくは、[異常値検出と貢献度分析の権限](#anomaly-detection-and-contribution-analysis-entitlements)を参照してください。

## 異常値検出

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出により、「ノイズ」から「真のシグナル」を分離し、これらのシグナルまたは異常値の潜在的な要因を特定できます。つまり、変則性の検出を使用すると、重要な統計変動と重要でない統計変動を識別できます。さらに、信頼できる指標（KPI）の予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上の低い注文の急増
* トライアル登録の急増または下落
* ランディングページ表示の下落
* ビデオバッファーイベントの急増
* ビデオの低ビットレートの下落

異常値検出と[貢献度分析](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/anomaly-detection/anomaly-detection)の双方が、Analysis Workspace の主要ワークフローです。毎日の異常値に対して貢献度分析を実行し、Analysis Workspace プロジェクトに結果を埋め込むことができます。

Analysis Workspace の異常値検出アルゴリズムには以下が含まれています。

* 既存の毎日の精度に加えて、1 時間ごと、毎週および毎月の精度のサポート
* シーズナリティ（「ブラックフライデー」など）や休日の認識

## 貢献度分析

貢献度分析では、データ内の隠れたパターンを見つけ出して、統計的な異常値を説明し、背後にある相関関係を特定します

* 予期しない顧客アクション、
* 範囲外の値、および
* 突然のスパイクまたはくぼみ

複数の収束するオーディエンスセグメントをまたいで選択された指標の場合。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ 貢献度分析 ](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


何かが発生しました。なぜですか？異常値検出レポートが、注文の指標で普通でないスパイクを示しています。普通とは異なる何が起こっているのでしょうか。誰がどのキャンペーンやリンクに反応したのでしょうか。何かが急速に広まったのでしょうか。この異常値に貢献した特定の要因は何でしょうか。そしておそらく最も重要なこととして、どうしたら顧客に関する重要な情報をつかむことができ、このパフォーマンスを繰り返すことができるのでしょうか（または、指標の急激な下降やネガティブな指標の急増が発生した場合、将来、どうすれば避けることができるでしょうか。）

貢献度分析は、データを即座に評価して、異常値が発生した原因を知るのに役立ちます。これまで数週間かかっていた、異常値に対する貢献の分類を数秒でおこない、オーディエンスセグメントのパターンを提供して、顧客インタラクションの成功パターンをプランすることを支援します。貢献度分析を戦略的に使用して、意味のある関連付けを特定し、取り込むことができます。 次に、これらの関連付けを戦略的に使用して、新しいオーディエンスセグメントを作成するか、戦術的に使用して、アラートをトリガーにする範囲外のアクティビティや不正なアクティビティを特定します。

[異常値検出](#anomaly-detection)は、選択した指標やオーディエンスセグメントの範囲で、データのスパイクや極端な統計的下降を特定します。異常値検出では、トレーニング期間に基づいて履歴基準を設定し、特定のイベントに関連する極端なオフセットをプロットします。 異常値検出では、貢献度分析による評価の対象となる統計的に関連するデータポイントをキャプチャして、肯定的な注文指標の急激な増加または否定的なバウンス指標の増加、またはその両方の減少を報告できます。 統計的な異常値が識別された次のステップとして、貢献度分析を使い、選択したデータポイントとの相関が高いマーケティングやキャンペーン関連の変数を発見することができます。高度なアルゴリズムと機械学習プロセスを実行して、大幅なスパイクまたは下降に貢献した関連性を自動で評価します。これらの計算がインタラクティブなビジュアライゼーションで表示され、なぜ異常が起こったのかや、どう対処すべきかを知るのに役立ちます。

貢献度分析は、異常値が発生した理由を説明するストーリーを開発するのに役立ちます。 また、異常値に対応する方法、関連する指標をキャプチャする方法、オーディエンスとのインタラクションの全体的な理由と顧客の興味のトレンドを示す隠れたポイントを特定する方法も説明します。 異常値には、2,000 艘のカヤックといった注文ミスなど、簡単に確認や修正をおこなえるものがあります。特定の対象キャンペーンにのみ反応する、ある地域である期間に現れるトレンドなど、複雑な場合もあります。様々なディメンションやその関連性の指標の貢献項目を総合すると、オーディエンスインタラクションの全体的なアイデアと、異常なデータポイントのコンテキストを得ることができます。

使用例を次に示します。

* 製品需要の変化を監視することで、リマーケティングの可能性を特定する。
* 特定のオーディエンスの興味に対応することで、顧客体験を強化する。
* 範囲外レポートで不正注文を早期に識別する。
* 大量のアクセスとダウンロード数を識別して、企業スパイから自社を守る。
* JavaScript タグが見つからないことをレポートするなどの監視操作。

異常値貢献度分析をスタートさせてしばらくすると、貢献度の高いトップアイテムが合計発生数と貢献度の値の項目の割合で並べられた貢献度の概要レポートが生成されます。正規化された貢献度スコアを使用すると、ディメンション間での比較、対象、関連度の調整ができます。

## 貢献度分析トークン

貢献度分析の権限を持つすべてのお客様は、Analysis Workspace 内で、毎月限られた回数だけ完全な貢献度分析を実行できます。貢献度分析 **ポイント商品（SiteCatalyst 15）のお客様** Analytics Foundation のお客様および Analytics Select のお客様で、貢献度分析の資格を持たないお客様を除外します。

会社ごとの実行回数は、会社が購入した Adobe Analytics 製品の種類に基づいて付与される月ごとのトークンによって制限されます。会社ごとの実行数には、トークンの誤用を防ぐために貢献度分析のアクセスを制限する機能が含まれています。

## よくある質問 {#section_11D0431AD2014B96AB9561CA66A367CE}

| 質問 | 回答 |
| --- | --- |
| アドビがトークンを導入した理由 | 貢献度分析は、Adobe Analytics の最も重要な機能の 1 つになりました。一部の Analytics 製品のようにディメンション数を 3 つに制限するのではなく、ごく限られた回数でも 1 か月に何度か完全な分析を行うことで、制限のない完全な貢献度分析のメリットを実感できます。 |
| 貢献度分析のトークンはどのように機能しますか。 プロジェクトに既存の貢献度分析を実装するときもトークンが必要ですか。それとも、新しい貢献度分析を実行するときにのみ、トークンが必要ですか。 | 各ログイン会社（各ユーザーではなく）は、1 か月あたり定められた数のトークンを入手します。これらのトークンを使用して、Analysis Workspace 内で「完全な」貢献度分析を実行できます。新しい貢献度分析を生成するたびにトークンが 1 つ必要です。事前実行された貢献度分析をプロジェクトに実装するときは、トークンは不要です。 |
| トークンを切らしていますが、さらに貢献度分析を実行したい場合はどうしますか。 | 別の Adobe Analytics 製品にアップグレードします。例えば、Standard（2 トークン／月）から Ultimate（20 トークン／月）にアップグレードします。これ以上トークンを購入することはできません。 既存のパッケージフレームワーク内でアップグレードする必要があります。 |
| 貢献度分析へのアクセスを制限するには、どのようにしますか。 | デフォルトでは、管理者のみが貢献度分析を実行するアクセス権を持っています。ただし、管理者は [Adobe Admin Console](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-console/home) に権限グループを作成することで、他のユーザーにアクセス権を付与できます。貢献度分析を使用する正当な理由があり、かつアクセス権を悪用しない信用できるユーザーに対してのみ、貢献度分析の使用権限を付与します。 この権限は、[!UICONTROL レポートスイートツール]の下で[!UICONTROL 貢献度分析]と呼ばれます。[詳細情報](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/permissions/report-suite-tools) |
| 1 か月あたり使用可能なトークン数は、どうすればわかりますか。また、当月に会社が使用したトークン数は、どうすればわかりますか。 | [!UICONTROL 管理者] ／ [!UICONTROL すべての管理者] ／ [!UICONTROL 会社設定ホーム] ／ [!UICONTROL 機能アクセスレベルを表示]に移動します。以下の下を見てください。<ul><li>貢献度分析：月使用トークンの数</li><li>貢献度分析：今月使用された使用トークンの数</li></ul> |

## 異常値検出と貢献度分析の権限 {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Analysis Workspace における異常値検出と貢献度分析の詳細な権限のリストを以下に示します。

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics の権限 </th> 
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
   <td colname="col3"> <p>1 ヶ月あたり 10 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり 20 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>トークン数に制限なし </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり 2 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（360、Attribution） </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり 2 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（Complete、<a href="https://business.adobe.com/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>） </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>トークン数に制限なし </p> </td> 
  </tr> 
 </tbody> 
</table>
