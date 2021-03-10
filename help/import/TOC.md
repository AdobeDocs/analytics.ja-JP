---
product: analytics
audience: end-user
user-guide-title: Analytics インポートガイド
breadcrumb-title: インポートガイド
user-guide-description: '一括またはリアルタイムで、外部のソースから Analytics にデータを取り込みます。 '
translation-type: tm+mt
source-git-commit: 946be738843a691a711cf6a84fd5556abbfb532d
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 97%

---


# Analytics インポートガイド {#import}

+ [Analytics インポートガイド](home.md)
+ データソース {#data-sources}
   + [データソースの概要](c-data-sources/datasrc-home.md)
   + [データソースの仕組み](c-data-sources/datasrc-how-data-sources-works.md)
   + [要件とアップロードに関する制限](c-data-sources/datasrc-requirements.md)
   + [データソース処理時間](c-data-sources/datasrc-processing-time.md)
   + [データソースを使用するための準備](c-data-sources/datasrc-preparing.md)
   + [データソースマネージャー](c-data-sources/datasrc-manager.md)
   + データソーステンプレート {#data-sources-template}
      + [データソーステンプレートの概要](c-data-sources/datasrc-template/datasrc-template-file.md)
      + [インポートファイルテンプレートの作成](c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md)
      + [インポートファイルの参照](c-data-sources/datasrc-template/datasrc-import-file-reference.md)
   + [データソースファイルのアップロード](c-data-sources/t-datasrc-uploading-data.md)
   + データのタイプとカテゴリ {#data-types-and-categories}
      + [データのタイプとカテゴリの概要](c-data-sources/c-datasrc-types/datasrc-categories.md)
      + [Web ログ](c-data-sources/c-datasrc-types/datasrc-web-log.md)
      + [トラフィック](c-data-sources/c-datasrc-types/datasrc-traffic.md)
      + [コンバージョン](c-data-sources/c-datasrc-types/datasrc-conversion.md)
      + [トランザクション ID](c-data-sources/c-datasrc-types/datasrc-transactionid.md)
      + [訪問者 ID](c-data-sources/c-datasrc-types/datasrc-visitorid.md)
      + [フル処理](c-data-sources/c-datasrc-types/datasrc-full-processing.md)
   + [トランザクションの統合と顧客の統合](c-data-sources/datasrc-integrating-offline-data.md)
   + [トランザクション ID と訪問者プロファイル](c-data-sources/datasrc-tid-visitor-profile.md)
   + [データソースに関する FAQ](c-data-sources/datasrc-faq.md)
+ [データ挿入 API](c-data-insertion-api/c-data-insertion-api.md)
+ Data Connectors {#dataconnectors}
   + [Analytics Data Connectors 使用の手引き](data-connectors/getting-started-data-connectors.md)
   + [Analytics Data Connectors の提供終了](data-connectors/data-connectors-eol.md)
   + Adobe Analytics 用 appFigures Data Connector {#appfigures}
      + [appFigures の概要](data-connectors/appfigures-overview/appfigures-overview.md)
      + [この統合をアクティブ化する前に](data-connectors/appfigures-overview/appfigures-before-activation.md)
      + [統合の設定](data-connectors/appfigures-overview/t-appfigures-integration.md)
      + [指標およびディメンション](data-connectors/appfigures-overview/appfigures-metrics.md)
      + [アプリデータのセグメント化](data-connectors/appfigures-overview/appfigures-segment-filter.md)
   + Adobe Analytics 用 Aprimo Data Connector {#aprimo}
      + [Adobe Analytics 用 Aprimo Data Connector](data-connectors/aprimo-overview/aprimo-overview.md)
      + [統合のアクティブ化](data-connectors/aprimo-overview/t-aprimo-activate.md)
      + [Adobe Analytics プラグインコード](data-connectors/aprimo-overview/aprimo-sitecatalyst-code.md)
   + Adobe Analytics 用 ContactLab Data Connector {#contactlab}
      + [Adobe Analytics 用 ContactLab Data Connector](data-connectors/c-contactlab-data-connector-for-adobe-analytics/c-contactlab-data-connector-for-adobe-analytics.md)
      + [統合のデプロイ](data-connectors/c-contactlab-data-connector-for-adobe-analytics/contactlab-deploying-the-integration.md)
   + Adobe Analytics 用 Datran Data Connector {#datran}
      + [Adobe Analytics 用 Datran Data Connector](data-connectors/datran-integration-overview/datran-integration-overview.md)
      + [Data Connectors 電子メール統合の準備](data-connectors/datran-integration-overview/datran-configuring-integration.md)
      + [Data Connectors 統合ウィザードの実行](data-connectors/datran-integration-overview/t-datran-wizard.md)
   + Adobe Analytics 用 Delivra Data Connector {#delivra}
      + [Adobe Analytics 用 Delivra Data Connector](data-connectors/delivra-integration-overview/delivra-integration-overview.md)
      + [Data Connectors 電子メール統合の準備](data-connectors/delivra-integration-overview/delivra-configuring-the-genesis-delivra-integration.md)
      + [Data Connectors 統合ウィザードの実行](data-connectors/delivra-integration-overview/t-delivra-running-the-genesis-integration-wizard.md)
   + Adobe Analytics 用 Demandbase Data Connector {#demandbase}
      + [Adobe Analytics 用 Demandbase Data Connector](data-connectors/demandbase-home/demandbase-home.md)
      + [統合のデプロイ](data-connectors/demandbase-home/demandbase-deploying.md)
      + [統合の使用](data-connectors/demandbase-home/demandbase-using-integration.md)
      + [Demandbase 標準ディメンション](data-connectors/demandbase-home/demandbase-standard-dimensions.md)
      + [Demandbase カスタムディメンション](data-connectors/demandbase-home/demandbase-custom-dimensions.md)
   + Adobe Analytics 用 DFA Data Connector {#dfa}
      + [DFA統合の提供終了情報](data-connectors/dfa-data-connector-analytics/dfa-eol.md)
      + [Adobe Analytics 用 DFA Data Connector](data-connectors/dfa-data-connector-analytics/dfa-data-connector-analytics.md)
      + [前提条件](data-connectors/dfa-data-connector-analytics/dfa-prerequisites.md)
      + [統合の機能](data-connectors/dfa-data-connector-analytics/dfa-integration-features.md)
      + [Analytics 変数とイベント](data-connectors/dfa-data-connector-analytics/dfa-analytics-variables-and-events.md)
      + [DFA 統合](data-connectors/dfa-data-connector-analytics/dfa-integration.md)
      + [DFA データを使用した Analytics レポート](data-connectors/dfa-data-connector-analytics/dfa-analytics-reports.md)
      + [指標の不一致の調整](data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md)
      + [よくある質問](data-connectors/dfa-data-connector-analytics/dfa-faq.md)
      + [最大遅延](data-connectors/dfa-data-connector-analytics/maxdelay.md)
   + Adobe Analytics 用 DreamMail Data Connector {#dreammail}
      + [Adobe Analytics 用 DreamMail Data Connector](data-connectors/dreammail-overview/dreammail-overview.md)
      + [統合のアクティブ化](data-connectors/dreammail-overview/t-dreammail-activate.md)
      + [Analytics プラグインコード](data-connectors/dreammail-overview/dreammail-analytics-code.md)
   + Adobe Analytics 用 Dynamic Signal VoiceStorm Data Connector {#dynamicsignal}
      + [Adobe Analytics 用 Dynamic Signal VoiceStorm Data Connector](data-connectors/dynamic-signal-for-analytics/dynamic-signal-for-analytics.md)
      + [統合のデプロイ](data-connectors/dynamic-signal-for-analytics/dynamic-signal-deploy-integration.md)
      + [統合の使用](data-connectors/dynamic-signal-for-analytics/dynamic-signal-use-integration.md)
   + Adobe Analytics 用 Emarsys Data Connector {#emarsys}
      + [Adobe Analytics 用 Emarsys Data Connector](data-connectors/emarsys-overview/emarsys-overview.md)
      + [Data Connectors 電子メール統合の準備](data-connectors/emarsys-overview/emarsys-configure-integration.md)
      + [Analytics 変数](data-connectors/emarsys-overview/emarsys-variables.md)
      + [Data Connectors 統合ウィザードの実行](data-connectors/emarsys-overview/emarsys-wizard.md)
   + Adobe Analytics 用 Kampyle Data Connector {#kampyle}
      + [Adobe Analytics 用 Kampyle Data Connector](data-connectors/kampyle-home/kampyle-home.md)
      + [統合のデプロイ](data-connectors/kampyle-home/kampyle-deploy.md)
      + [統合の使用](data-connectors/kampyle-home/kampyle-integration.md)
   + Adobe Analytics 用 Lyris Data Connector {#lyris}
      + [Adobe Analytics 用 Lyris Data Connector](data-connectors/lyris-overview/lyris-overview.md)
      + [統合のデプロイ](data-connectors/lyris-overview/lyris-deploy-integration.md)
   + Adobe Analytics 用 Neolane Ozon Data Connector {#neolane}
      + [Adobe Analytics 用 Neolane Ozon Data Connector](data-connectors/neolane-overview/neolane-overview.md)
      + [統合のアクティブ化](data-connectors/neolane-overview/neolane-activate.md)
      + [Adobe Analytics プラグインコード](data-connectors/neolane-overview/neolane-plugin-code.md)
   + Adobe Analytics 用 Optivo BroadMail Data Connector {#optivo}
      + [Adobe Analytics 用 Optivo BroadMail Data Connector](data-connectors/optivo-overview/optivo-overview.md)
      + [統合のアクティブ化](data-connectors/optivo-overview/optivo-activate.md)
      + [Adobe Analytics プラグインコード](data-connectors/optivo-overview/optivo-plugin-code.md)
   + Adobe Analytics 用 Qualtrics Data Connector {#qualtrics}
      + [Adobe Analytics 用 Qualtrics Data Connector](data-connectors/qualtrics-overview/qualtrics-overview.md)
      + [統合のデプロイ](data-connectors/qualtrics-overview/qualtrics-deploying.md)
      + [統合の使用](data-connectors/qualtrics-overview/qualtrics-integration.md)
      + [Qualtrics 組織 ID の検索](data-connectors/qualtrics-overview/qualtrics-org-id.md)
      + [Qualtrics Adobe Analytics トークンの生成](data-connectors/qualtrics-overview/qualtrics-token.md)
   + Adobe Analytics 用 Responsys Data Connector {#responsys}
      + [Adobe Analytics 用 Responsys Data Connector](data-connectors/responsys-home/responsys-home.md)
      + [統合のデプロイ](data-connectors/responsys-home/responsys-deploy/responsys-deploy.md)
      + [統合の確認](data-connectors/responsys-home/responsys-verify.md)
   + Adobe Analytics 用 Selligent Data Connector {#selligent}
      + [Adobe Analytics 用 Selligent Data Connector](data-connectors/selligent-overview/selligent-overview.md)
      + [統合のデプロイ](data-connectors/selligent-overview/selligent-deploy-integration.md)
      + [クエリー文字列パラメータープラグインコード](data-connectors/selligent-overview/selligent-plugin-code.md)
   + Adobe Analytics 用 Silverpop Data Connector {#silverpop}
      + [Adobe Analytics 用 Silverpop Data Connector](data-connectors/silverpop-overview/silverpop-overview.md)
      + [この統合をアクティブ化する前に](data-connectors/silverpop-overview/silverpop-before-activation/silverpop-before-activation.md)
      + [Analytics 統合変数](data-connectors/silverpop-overview/silverpop-variables.md)
      + [Silverpop 統合](data-connectors/silverpop-overview/silverpop-wizard.md)
      + [Analytics プラグインコード](data-connectors/silverpop-overview/silverpop-analytics-code.md)
+ 使用例のインポート{#use-cases}
   + [データソースを使用した有料検索指標のインポート](use-cases/paid-search-metrics.md)
