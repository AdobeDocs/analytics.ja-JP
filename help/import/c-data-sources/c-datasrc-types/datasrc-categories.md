---
description: データソースのカテゴリは、提供する機能の類似性に基づいて様々なデータソースのタイプを識別します。
subtopic: Data sources
title: データのタイプとカテゴリの概要
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: ht
source-wordcount: '903'
ht-degree: 100%

---

# データのタイプとカテゴリの概要

データソースのカテゴリは、提供する機能の類似性に基づいて様々なデータソースのタイプを識別します。

カテゴリによって、ユーザーの視点でデータソースをグループ分けすることができます。[!DNL Data Sources] UI からデータソースを作成する場合、まずデータソースのカテゴリを選択してから、データソースのタイプを指定します。各カテゴリに含まれるデータソースのタイプは、類似したタイプのデータをサポートしています。[!DNL Data Sources] は次のデータソースカテゴリを提供します。

## web サイトの使用状況 {#web-usage}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL web サーバーログファイル] | [web ログ](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | 大部分の Web サーバーは、提供したすべてのページを記録するログファイルを生成しています。このデータソースを使用すると、大部分の Web サーバーデータからのログファイルを処理してレポートに追加することができます。 |
| [!UICONTROL Advertising Cloud のバルクアップロード] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 手動の、または Excel で自動化したバルクアップロードを [!DNL Advertising Cloud] で実行できます。 |
| [!UICONTROL サイトレベルのトラフィックデータソース] | [トラフィック](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | web サイト全体のトラフィックデータを読み込みます。例：[!UICONTROL Page_Views]。 |
| [!UICONTROL 分類トラフィックデータソース] | [トラフィック](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | 別の web サイト変数で分類されたトラフィックデータを読み込みます。例： [!UICONTROL 製品] ごとに分類された [!UICONTROL ページ表示数 ]。 |

## 広告キャンペーン {#ad-campaigns}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 汎用広告サーバー] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 広告サーバーの広告アクティビティのインプレッションおよびその他のトップライン指標をマーケティングレポート内に組み込むことができます。これは汎用の広告サーバーデータソースであり、特定の広告サーバーがサポートされていない場合に使用します。 |
| [!UICONTROL 汎用電子メールキャンペーンサーバー] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 電子メールキャンペーンサーバーにある指標をマーケティングレポート内に統合できます。一般的に統合される指標は、送信されたメッセージ数、配信されたメッセージ数、読まれたメッセージ数などです。これは汎用の電子メールキャンペーンデータソースであり、特定の電子メールキャンペーンサーバーがサポートされていない場合に使用します。 |
| [!UICONTROL 汎用ペイパークリックサービス] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | インプレッション、クリック数、コストなど、クリック課金の実績に関するデータを読み込むことができます。これは汎用のペイパークリックデータソースであり、特定のペイパークリックサービスがサポートされていない場合に使用します。 |

## 顧客関係管理（CRM） {#crm}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 汎用コールセンター] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | コールセンターに関する情報をマーケティングレポート内に組み込むことができます。比較的よく読み込まれる指標として、通話回数、通話時間、エージェント名、合計販売額などがあります。これは汎用のコールセンターデータソースであり、特定のコールセンターソフトウェアがサポートされていない場合に使用します。 |
| [!UICONTROL 汎用顧客サポートアプリケーション] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | カスタマーサポートソフトウェアに関する情報をマーケティングレポート内に組み込むことができます。新規サポート件数、解決したサポート件数、およびサポート解決の所要時間などの指標が含まれます。これは汎用の顧客サポートデータソースであり、特定の顧客サービスアプリケーションがサポートされていない場合に使用します。 |

## 顧客満足度 {#csat}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 汎用調査データ] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | サードパーティのツールから得た調査結果をマーケティングレポート内に組み込むことができます。これにより、サイトでの顧客のインタラクションを基に顧客の全体的な満足度がわかります。これは汎用の調査データソースであり、特定の調査データサービスがサポートされていない場合に使用します。 |

## サイトのパフォーマンス {#performance}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 汎用サイトダウンロード速度] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | ダウンロードの速度を追跡するアプリケーションまたはサービスから得たデータを、利用しているデータに統合できます。これは汎用のダウンロード速度データソースであり、特定のダウンロード速度測定ソフトウェアまたはサービスがサポートされていない場合に使用します。 |

## 汎用 {#generic}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 一般的なデータソース（概要データのみ）] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | このデータソースは、マーケティングレポートおよび Analytics に読み込むデータと似たタイプがない場合に使用します。 |
| [!UICONTROL 一般的なデータソース（フル処理）] | フル処理 | アドビは、2022年1月31日（PT）にフル処理データソースを非推奨（廃止予定）としました。[詳細情報](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). 代わりに、[Bulk Data Insertion API（BDIA）](https://www.adobe.io/apis/experiencecloud/analytics/docs.html?lang=ja)を使用することをお勧めします。 |
| [!UICONTROL 一般的なデータソース（トランザクション ID）] | <ul><li>トランザクション ID</li><li>訪問者 ID</li></ul> | 任意のオフラインイベントをオンラインイベントに関連付けることができます。[!UICONTROL トランザクション ID] は、オフラインイベントとオンラインイベント間のキーとして機能します。 |

## オンライン購入 {#purchases}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 製品の返品数] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 製品の返品データを読み込んで購入 ID に関連付けることによって、返品につながる可能性の高い検索エンジン、キーワード、キャンペーンなどの属性を特定することができます。 |
| [!UICONTROL 製品コスト] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | web サイトから購入および発送された製品の実際のコストを確認できます。コストまたは利益を各製品に関連付けることで、web サイトで最も利益を上げたキャンペーン、キーワード、社内プロモーションを正確に報告できます。 |
| [!UICONTROL 注文ステータス] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 指標を使用して、発注されたすべての注文のステータス（キャンセルされた注文、発送済みの注文、完了した注文、不正と見なされる注文など）を特定できます。注文ステータスレポートでは、注文完了率が最も高い獲得方法を特定できます。 |

## リード数と見積もり数 {#leads}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL リードジェネレーション] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | web サイトで発生したすべてのリードについて、実際に発生した売上高を含め、リードの結果に関する情報をアップロードできます。売上高をリード ID に正確に関連付けることで、最も利益を上げたキャンペーンとプロモーションを特定できます。 |
| [!UICONTROL オンラインの見積もり] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | web サイトで発生したすべてのリードについて、実際に発生した売上高を含め、リードの結果に関する情報をアップロードできます。売上高をリード ID に正確に関連付けることで、最も利益を上げたキャンペーンとプロモーションを特定できます。 |
| [!UICONTROL コールセンターデータ] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | コールセンタートランザクションをアップロードして、顧客の電話に結びついた方策（キャンペーンやプロモーションなど）を特定できます。 |
