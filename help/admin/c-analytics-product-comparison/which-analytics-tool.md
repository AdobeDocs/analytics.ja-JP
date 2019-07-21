---
description: このヘルプページでは、各 Adobe Analytics ツールの推奨される使用例が紹介されています。ここにリストされている順にツールを検討するとよいでしょう。あるツールがニーズを満たさない場合は、次のツールの使用を検討します。
seo-description: このヘルプページでは、各 Adobe Analytics ツールの推奨される使用例が紹介されています。ここにリストされている順にツールを検討するとよいでしょう。あるツールがニーズを満たさない場合は、次のツールの使用を検討します。
seo-title: どのAdobe Analyticsツールを使用する必要がありますか。
title: どのAdobe Analyticsツールを使用する必要がありますか。
uuid: 1179e49d-3cfc-4abd- a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: bf9152741507c75e1f92e8d5d515127eadf5d590

---


# どのAdobe Analyticsツールを使用する必要がありますか。

このヘルプページでは、各 Adobe Analytics ツールの推奨される使用例が紹介されています。ここにリストされている順にツールを検討するとよいでしょう。あるツールがニーズを満たさない場合は、次のツールの使用を検討します。

Adobe Analytics の製品比較について詳しくは、[こちら](../../admin/c-analytics-product-comparison/analytics-product-comparison.md#concept_D9DB9FA42CA04F4C97765B6B31A0005D)を参照してください。

## Adobe Analytics レポートユーザーインターフェイス {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)** は、レポートおよび分析のあらゆるニーズに応える中心的なユーザーインターフェイスです。アドビでは、この製品への投資を続け、毎月、製品のアップデートをリリースしています。Analysis Workspaceで実行できないタスクがある場合は、以下のインターフェイスを考慮してください。**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** は以下の場合に使用します。

* ナビゲーションが容易な作成済みのレポートにアクセスする必要がある初心者ユーザーの場合。
* A4T アクティビティのインプレッション数およびコンバージョン数を正確に把握する。
* Target アクティビティ（Analytics for Target／A4T）の上昇率と信頼性を把握する。
* UI でリアルタイムデータにアクセスする。
* カレンダーイベントをセットアップする。
* ターゲットをセットアップする。
* ボットレポートを表示する。
* 単一の UI ダッシュボードで複数のレポートスイートを表示する。
* 同時ビューア、ビデオ視聴時間帯、ビューアドロップオフの独自のビデオビジュアライゼーションにアクセスする。
* 予定レポートで発行リストを活用する。

**[Mobile Services UI](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)** は以下の場合に使用します。

* モバイルアプリデータのサイロ型表示が求められる場合。
* モバイルアプリ SDK の実装を管理する。
* アプリ内メッセージ、プッシュメッセージ、場所のターゲット設定などのモバイル広告を設定する。
* アプリデータのよりインタラクティブな可視化が求められる場合（サンバースト）。
* マップ上に目標地点を視覚化する。
* 全期間値の指標。

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)** は以下の場合に使用します。

* 真の表ビルダー機能が求められる場合。例えば、a) 作成する必要のある表が Analysis Workspace でサポートされていない場合、b) 表を再作成するタイミングを制御できるようにする場合、c) すべての行に適用する様々な分類レベルを表に記憶させる場合、d) 指標行の順序を手動で設定する場合など
* 50,000 行ものデータのエクスポート
* プロジェクト作業のタブ編成が求められる場合。
* サイト分析レポートを使用する（3D パスレポート）。

**[Data Workbench](https://marketing.adobe.com/resources/help/en_US/insight/)** は以下の場合に使用します。

* 柔軟性の最も高い Analytics ツールとして使用（訪問者レベル、ヒットレベル分析に至るまで対応）。
* CRM から POS さらに Web へのオンラインおよびオフラインインタラクションのマルチチャネルデータセットを作成する。
* 高度なアトリビューション（ルールベースモデルおよびアルゴリズムモデル）。
* 予測、統計的モデリング（傾向スコアリング、クラスタリング、相関関係など）。
* 待ち時間分析（イベント前後の時間）。
* Adobe Experience Cloud 全体での複雑なセグメントの識別およびエクスポート。

## Adobe Analytics へのデータのインポート {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[分類](/help/components/c-classifications2/c-classifications.md)**&#x200B;は以下の場合に使用します。

* 収集値（eVar、プロパティ、マーケティングチャネル）に関連付けるメタデータがある場合
* オプション

   * ルールビルダー：変数に収集中の書式設定された予測可能な値（例えば、区切り値など）がある場合に使用します。このアプローチでは、ルールを一度設定したら、後はほとんど自動化できます。
   * ブラウザーインポーター：予測可能な値がない場合か、1 回限りの更新が必要な有限の値リストがある場合に使用します。このアプローチでは、新しい値の分類を継続的に監視する必要があります。

**[データソース](/help/import/c-data-sources/datasrc-home.md)**&#x200B;は以下の場合に使用します。

* Adobe Analytics に恒久的に書き込むオフラインデータがある場合
* オプション:

   * 概要：単純なデータのアップロード（日単位または限定ディメンション）。
   * トランザクション ID：オンラインエンドポイントをオフラインデータに接続し、インポートしたデータを、オンラインでキャプチャした訪問者スナップショットに完全に関連付けるデータアップロード（例えば、注文がオンラインで完了し、オフラインで返されるなど）。
   * フル処理：タイムスタンプ付きのデータソース。Adobe サーバーで収集されたヒットのように処理されます。つまり、データが訪問者のジャーニーに直接挿入されます。

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)（以前の Genesis）**&#x200B;は以下の場合に使用します。

* Adobe Analytics とのサポートされる接続を構築したサードパーティプロバイダーとやり取りする場合。Data Connectors は、通常、サマリレベルのデータを、定期的、恒久的かつ自動的に Adobe Analytics に取り込みます。

**[Data Insertion API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)** は以下の場合に使用します。

* データを Adobe Analytics にアップロードする必要があるときに Adobe AppMeasurement またはモバイル SDK コードを使用できない場合。

**[顧客属性](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**&#x200B;は以下の場合に使用します。

* 顧客関係管理（CRM）データベースに取り込んだエンタープライズ顧客データを Experience Cloud にアップロードする場合。
* CRM データを Analytics でより詳しく分析する場合または Adobe Target のターゲティング条件として使用する場合。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** は以下の場合に使用します。

* 人口統計情報（例：性別や所得水準）、サイコグラフィック情報（例：興味や趣味）、CRM データ、広告インプレッションデータなどの Adobe Audience Manager（AAM）のオーディエンスデータを任意の Analytics ワークフローに組み込む場合。
* この統合によって新しい情報が Analytics にヒットごとに送信されるので、アップロードされた CRM データを時間ベースにする場合。

## Adobe Analytics からのデータのエクスポート {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)** は以下の場合に使用します。

* Workspace のカスタマイズされたレイアウトオプションが制限的である場合（Report Builder では Excel の範囲内であればどのようなレイアウトも可能）。
* ユーザー入力またはオフラインデータソース（インプレッション数、コスト）の Adobe データへの緩やかな統合。データを統合するためのより恒久的なソリューションはデータソースです（Adobe Analytics へのデータのインポートを参照）。
* 様々なディメンションのレポートから得られるデータの結合（例えば、プロモーションのインプレッションレポートとプロモーションのクリックトゥコンバージョンレポートの結合など）。
* クロスレポートスイート表示。
* スケジュール設定による自動化が求められる場合（XLSX、XLSM、CSV、PDF、TXT、XML、MHT）。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** は以下の場合に使用します。

* UIに表示されない変数（IPアドレス、エクスペリエンスクラウドID、Analytics訪問者ID、ページURL）にアクセスするには
* UI よりも詳細なデータへのアクセス（非正規化テーブル表示）
* ピボットテーブルの入力に適した形式でのデータのダウンロード 
* 顧客が Adobe データをサードパーティ製のデータ可視化ツールに入力することを希望する場合（ヒットレベルではなく、若干要約されたデータ）
* すべての個別ディメンション値へのアクセス（Adobe Analytics で「低トラフィック」を検出した場合）

**[Analyticsデータフィード](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** を使用する必要があります。

* アドビが提供する最も詳細なデータフィード（訪問者 ID、ヒット）の利用。
* 顧客がアドビのデータを（送信可能な最も詳細なレベルで）顧客側のデータベースに格納したい場合。
* 顧客がビジネスインテリジェンス（BI）ツールの開発を希望する場合や、ヒットレベルのアドビのデータをサードパーティ製ツールに入力しようと考えている場合。

**[レポート API](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)** は、その他の可視化オプションがニーズを満たさない場合に使用します。次の 3 つの API オプションがあります。

* **処理済み**：機能豊富なデータ（訪問、訪問者、セグメントなど）が必要な場合。これは典型的な Analytics UI の要約データで、30 分から 90 分で提供されます。Report Builder を通じて使用できます。
* **リアルタイム**：いくつかの指標とディメンションを数秒の待ち時間で表示させる場合。これは、限定的な、部分的に処理され要約されたデータで、30 秒以内で提供されます。最頻使用、勝者、敗者の固有アルゴリズムが含まれます。Report Builder を通じて使用できます。
* **[!UICONTROL ライブストリーム]**：部分的に処理されたヒットレベルの Analytics データのストリームを数秒以内で収集したい場合。これは部分的に処理されたデータで、30 秒以内で提供されます。Analytics Premium でのみ使用可能です。データを可視化する何らかの方法が必要になります。通常は、エンジニアリングサービスを使用しておこないます。

## カスタムソリューション {#section_4A212F26A15947599DFB0399A0440CB6}

エンジニアリングサービスは、次のような場合に使用します。:

* その他の Adobe ツールがニーズを満たさない。
* カスタムエクスペリエンスが必要。
* 完全に自動化されたソリューションを求めている。
* 多くのデバイスにリーチしたい。
* 複数のデータソースがある。
* 複雑なデータの ETL（抽出-変換-読み込み）に関する要件がある。
* カスタムブランディングが必要。
* [!UICONTROL Analytics ライブストリーム]の可視化が必要。
