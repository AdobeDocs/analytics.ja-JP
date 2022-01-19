---
description: データソースのカテゴリは、提供する機能の類似性に基づいて様々なデータソースのタイプを識別します。
subtopic: Data sources
title: データのタイプとカテゴリの概要
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 91%

---

# データのタイプとカテゴリの概要

データソースのカテゴリは、提供する機能の類似性に基づいて様々なデータソースのタイプを識別します。

カテゴリによって、ユーザーの視点でデータソースをグループ分けすることができます。を使用してデータソースを作成する場合 [!DNL Data Sources] UI で、まずデータソースのカテゴリを選択し、次に特定のデータソースタイプを選択します。 各カテゴリに含まれるデータソースのタイプは、類似したタイプのデータをサポートしています。[!DNL Data Sources] は次のデータソースカテゴリを提供します。

## Web サイトの使用状況 {#web-usage}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL Web サーバーログファイル] | [Web ログ](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | 大部分の Web サーバーは、提供したすべてのページを記録するログファイルを生成しています。このデータソースを使用すると、大部分の Web サーバーデータからのログファイルを処理してレポートに追加することができます。 |
| [!UICONTROL Advertising Cloud のバルクアップロード] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 手動および Excel で自動化したバルクアップロードをで実行できます。 [!DNL Advertising Cloud]. |
| [!UICONTROL サイトレベルのトラフィックデータソース] | [トラフィック](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Web サイト全体のトラフィックデータをインポートします。例： [!UICONTROL ページビュー数]. |
| [!UICONTROL 分類トラフィックデータソース] | [トラフィック](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | 別の Web サイト変数で分類されたトラフィックデータをインポートします。例： [!UICONTROL ページビュー数] 次の項目で分類： [!UICONTROL 製品]. |

## 広告キャンペーン {#ad-campaigns}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 汎用広告サーバー] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 広告サーバーの広告アクティビティのインプレッションおよびその他のトップライン指標をマーケティングレポート内に組み込むことができます。これは汎用の広告サーバーデータソースであり、特定の広告サーバーがサポートされていない場合に使用します。 |
| [!UICONTROL 汎用電子メールキャンペーンサーバー] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 電子メールキャンペーンサーバーにある指標をマーケティングレポート内に統合できます。一般的に統合される指標は、送信されたメッセージ数、配信されたメッセージ数、読まれたメッセージ数などです。これは汎用の電子メールキャンペーンデータソースであり、特定の電子メールキャンペーンサーバーがサポートされていない場合に使用します。 |
| [!UICONTROL 汎用ペイパークリックサービス] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | インプレッション、クリック数、コストなど、ペイパークリックの実績に関するデータをインポートできます。これは汎用のペイパークリックデータソースであり、特定のペイパークリックサービスがサポートされていない場合に使用します。 |

## 顧客関係管理（CRM） {#crm}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 汎用コールセンター] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | コールセンターに関する情報をマーケティングレポート内に組み込むことができます。比較的よくインポートされる指標として、通話回数、電話使用時間、エージェント名、合計販売額などがあります。これは汎用のコールセンターデータソースであり、特定のコールセンターソフトウェアがサポートされていない場合に使用します。 |
| [!UICONTROL 汎用顧客サポート アプリケーション] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | カスタマーサポートソフトウェアに関する情報をマーケティングレポート内に組み込むことができます。新規サポート件数、解決したサポート件数、およびサポート解決の所要時間などの指標が含まれます。これは汎用の顧客サポートデータソースであり、特定の顧客サービスアプリケーションがサポートされていない場合に使用します。 |

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
| [!UICONTROL 一般的なデータソース（サマリデータのみ）] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | このデータソースは、マーケティングレポートおよび Analytics にインポートするデータに近いタイプがない場合に使用します。 |
| [!UICONTROL 一般的なデータソース（フル処理）] | フル処理 | Adobeは、2022 年 1 月 31 日にフル処理データソースを非推奨（廃止予定）となりました。 [詳細情報](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). Adobeでは、 [一括データ挿入 API (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) 代わりに、 |
| [!UICONTROL 一般的なデータソース（トランザクション ID）] | <ul><li>トランザクション ID</li><li>訪問者 ID</li></ul> | 任意のオフラインイベントをオンラインイベントに関連付けることができます。この [!UICONTROL トランザクション ID] は、オフラインイベントとオンラインイベントの間のキーとして機能します。 |

## オンライン購入 {#purchases}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL 製品の返却数] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 製品返却データをインポートして購入 ID に関連付けることによって、返品につながる可能性の高い検索エンジン、キーワード、キャンペーンなどの属性を特定することができます。 |
| [!UICONTROL 製品コスト] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Web サイトから購入および発送された製品の実際のコストが得られます。コストまたは利益を各製品に関連付けることで、Web サイトで最も利益を上げたキャンペーン、キーワード、社内プロモーションに関して正確なレポートが得られるようになります。 |
| [!UICONTROL 注文ステータス] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 指標を使用して、発注されたすべての注文のステータス（キャンセルされた注文、発送済みの注文、完了した注文、不正と見なされる注文など）を特定します。注文ステータスレポートでは、注文完了率が最も高い獲得方法を特定できます。 |

## リード数と見積もり数 {#leads}

| データソース | 処理タイプ | 説明 |
| --- | --- | --- |
| [!UICONTROL リードジェネレーション] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Web サイトで発生したすべてのリードについて、実際に発生した売上高を含む、リード数の結果に関する情報をアップロードできます。売上高をリード ID に正確に関連付けることで、最も利益を上げたキャンペーンとプロモーションを特定できます。 |
| [!UICONTROL オンラインの見積もり] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Web サイトで発生したすべてのリードについて、実際に発生した売上高を含む、リード数の結果に関する情報をアップロードできます。売上高をリード ID に正確に関連付けることで、最も利益を上げたキャンペーンとプロモーションを特定できます。 |
| [!UICONTROL コールセンターデータ] | [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | コールセンタートランザクションをアップロードして、顧客の電話に結びついた方策（キャンペーンやプロモーションなど）を特定できます。 |
