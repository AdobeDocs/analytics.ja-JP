---
description: API アクセス、レポートスイートの管理、ツールとレポートおよびダッシュボードの項目に関するユーザー権限を有効にします。
keywords: グループ;権限
subtopic: Users and groups
title: レポートスイートツールの権限のカスタマイズ
topic: Admin tools
uuid: 3c95d296-ffd0-4971-9c5f-110ddbe042ce
translation-type: tm+mt
source-git-commit: 89a5524ac0e96d63acd54c2ef3e22c17314f332d
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 93%

---


# レポートスイートツールの権限のカスタマイズ

>[!IMPORTANT]
>
>ユーザーおよび製品管理は、[Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移行されます。ユーザーを移行する時期は、アドビから通知されます。すべての顧客が移行されたら、**[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**／**[!UICONTROL ユーザー管理]**&#x200B;のヘルプコンテンツは利用できなくなります。

API アクセス、レポートスイートの管理、ツールとレポートおよびダッシュボードの項目に関するユーザー権限を有効にします。

**[!UICONTROL ユーザー管理]**／**[!UICONTROL グループ]**／**[!UICONTROL レポートアクセス]**／**[!UICONTROL レポートスイートツール]**／**[!UICONTROL カスタマイズ]**

[!UICONTROL レポートスイートツールのカスタマイズ]ページでは、グループのメンバーに次の項目へのアクセス権を付与します。

![](assets/report-suite-tools.png)

## フィールドの説明

このページの設定は、[!UICONTROL ユーザーグループの定義]ページで選択されたレポートスイートに関係します。

| 要素 | 説明 |
|--- |--- |
| **Web サービス** |  |
| これらの設定を使用すると、ユーザーは Data Warehouse メソッドに対する呼び出しをおこなって、レポートスイート設定を引き出すことができます。 |  |
| Data Warehouse | 管理者以外のユーザーが Web サービス API で Data Warehouse メソッドを使用して呼び出しをおこなうことができます。[Data Warehouse - 開発者向けドキュメント](/help/export/data-warehouse/data-warehouse.md)を参照してください。 |
| レポート スイート（読み取り） | 管理者以外のユーザーが API のレポートスイートメソッドを使用できます。 |
| レポート スイート（書き込み） | 管理者以外のユーザーが API のレポートスイートメソッドを使用できます。 |
| **レポートスイートの管理** |  |
| これらの設定は、管理者／レポートスイート／設定を編集のメニュー項目にアクセス権を付与します（[Report Suite Manager](/help/admin/c-manage-report-suites/report-suites-admin.md)） |  |
| [トラフィック管理](/help/admin/c-traffic-management/traffic-management.md) | トラフィック管理に対する権限を付与します。 |
| [レポートスイートの管理](/help/admin/c-manage-report-suites/report-suites-admin.md) | レポートスイートを管理する権限を付与します。 |
| [アカウントの概要](/help/admin/admin/general-acct-settings-admin.md) | レポートスイートのアカウント設定を編集する権限を付与します。 |
| [URL フィルター](/help/admin/admin/internal-url-filter-admin.md) | レポートスイートの内部 URL フィルターに対する権限を付与します。内部 URL フィルターは、サイト内部のリファラー（参照ページ）を識別するために使用されます。 |
| [カスタムカレンダー](/help/admin/admin/custom-calendar.md) | カスタムカレンダーを編集する権限を付与します。 |
| [有料検索](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) | 有料検索探知は、検索エンジンと検索キーワードレポート内の自然検索と有料検索を区別します。 |
| [メニューのカスタマイズ](/help/admin/admin/customize-menus.md) | Reports &amp; Analytics でユーザーに表示されるレポートメニューをカスタマイズします。 |
| [リアルタイムレポート設定](/help/admin/admin/realtime/t-realtime-admin.md) | Analytics でリアルタイムレポートを設定する権限です。 |
| [ビデオ設定](/help/admin/admin/video-management.md) | ビデオのトラッキングとレポートに使用されるカスタムコンバージョン変数（eVar）とカスタムイベントのセットを指定する権限です。 |
| [ビデオ分類](https://docs.adobe.com/content/help/ja-JP/media-analytics/using/media-overview.html) | ビデオのトラッキングとレポートに使用されるカスタムコンバージョン変数（eVar）とカスタムイベントのセットを指定する権限です。 |
| [トラフィック変数](/help/admin/admin/c-traffic-variables/traffic-var.md) | カスタムデータを特定のトラフィック関連イベントに相互に関連付ける権限です。 |
| [トラフィック分類](/help/admin/admin/c-traffic-variables/traffic-classifications.md) | （ツールとレポートの）分類に統合されました。 |
| [チャネル](/help/components/c-marketing-channels/analyze-mc.md) | Report Suite Manager／設定を編集／マーケティングチャネルのマーケティングチャネル設定に対する権限を付与します。 |
| [コスト](https://docs.adobe.com/content/help/ja-JP/analytics/components/marketing-channels/analyze-mc.html) | Report Suite Manager のマーケティングチャネル／マーケティングチャネルのコスト設定に対する設定を有効にします。 |
| [コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) | カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。 |
| [検索方法](/help/admin/admin/finding-methods.md) | 各種の検索方法レポートがサイト上のコンバージョンの成功イベントのクレジットを受け取る方法を特定できます。 |
| [コンバージョンの分類](/help/admin/admin/conversion-var-admin/conversion-classifications.md) | （ツールとレポートの）分類に統合されました。 |
| [個別訪問者](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/unique-visitor-variable/t-unique-visitor-variable.html) | 個別訪問者変数を指定する権限を付与します。 |
| [成功イベント](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) | 製品表示、チェックアウト、購入など、トラッキングできるアクション。 |
| [分類階層](/help/admin/admin/conversion-var-admin/classification-hierarchies.md) | （ツールとレポートの）分類に統合されました。 |
| [リスト変数](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/page-vars/page-variables.html) | リスト Var とも呼ばれます。リスト Prop の機能と同様、リスト Var は同じイメージリクエスト内で複数の値を同時にセットできます。 |
| [デフォルトの指標](/help/admin/admin/default-metrics.md) | ユーザーがカスタム指標のセットを選択しない限り、Reports &amp; Analytics ではすべてのコンバージョンレポートでデフォルトの指標セットが表示されます。選択した指標は、関連付けられたレポートスイートのすべてのユーザーに表示されます。 |
| [処理ルール](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) | データ収集をシンプル化し、レポートに送信されるコンテンツを管理する処理ルールへのアクセス権を付与します。 |
| **ツールとレポート** |  |
| [異常値検出](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=ja-JP) | 以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法である、異常値検出に対する権限を付与します。 |
| [チャネルレポート](/help/components/c-marketing-channels/analyze-mc.md) | レポート／マーケティングチャネルレポートにあるマーケティングチャネルレポートに対する権限を付与します。 |
| [リアルタイムレポート](/help/admin/admin/realtime/t-realtime-admin.md) | リアルタイムレポートへのアクセス権を付与します。 |
| [ボットページ](/help/admin/admin/bot-removal/bot-rules.md) | **注意：ボットページは、ボットルールの管理ではなく、特定のReports &amp; Analyticsレポート用です。現在、ボットルールの編集を許可する権限はありません。**&#x200B;ボットルールを使用すると、既知のスパイダーやボットによって生成されるトラフィックを、レポートスイートから削除できます。ボットトラフィックを削除することで、Web サイトでのユーザーアクティビティをより正確に測定できるようになります。 |
| [ボット](/help/admin/admin/bot-removal/bot-rules.md) | **注意：ボットは、ボットルールの管理ではなく、特定のReports &amp; Analyticsレポート用です。現在、ボットルールの編集を許可する権限はありません。** ボットを使用すると、既知のスパイダーやボットによって生成されるトラフィックを、レポートスイートから削除できます。ボットトラフィックを削除することで、Web サイトでのユーザーアクティビティをより正確に測定できるようになります。 |
| [カスタム Data Warehouse レポート](/help/export/data-warehouse/data-warehouse.md) | Data Warehouse は、カスタムレポート用の処理されていない生のデータを取り出す機能です。カスタムレポートはこのデータをフィルタリングして実行します。ユーザー独自の質問に基づいて、生データから詳細なデータの関連性を表示するようレポートにリクエストできます。 |
| 日別再来訪 | （レガシー）ある特定の日に、Web サイトを 2 回以上訪ねた訪問者の数を表示するレポートです。1 日は直前の 24 時間として定義されます。 |
| [データソースマネージャー](/help/admin/admin/data-sources.md) | データソース機能を使用すると、オフラインソースから Analytics にデータをインポートできます。 |
| [IP アドレスで除外](/help/admin/admin/exclude-ip.md) | レポートから、社内の Web サイト活動、サイトのテスト、従業員の使用量など、特定の IP アドレスからのデータを除外できます。 |
| レガシー ClickMap | レガシー ClickMap オーバーレイツールへのアクセス権を付与します。 |
| レガシー ClickMap のインストール | レガシー ClickMap ツールにインストール権限を付与します。 |
| 再来訪 | 訪問回数が 2 以上である訪問の数を示すレポート。再来訪レポートには、cookie を使用していない訪問者が含まれます。 |
| [分類インポーター](https://docs.adobe.com/content/help/ja-JP/analytics/components/classifications/classifications-importer/c-working-with-saint.html) / エクスポーターおよび[ルールビルダー](https://docs.adobe.com/content/help/ja-JP/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html) | 分類に統合されました（以下を参照してください）。 |
| データフィードマネージャー | Grants rights to theAnalytics データフィードに権限を付与します。 |
| 分類 | 「トラフィック分類」、「ビデオ分類」、「コンバージョンの分類」、「分類階層」、「分類マネージャー」および「分類インポーター／エクスポーターおよびルールビルダー」の権限がまとめられています。注意：この権限を持つユーザーは、選択したレポートスイートだけではなく、すべてのレポートスイートの分類を編集できます。 |
| [貢献度分析](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) | Analysis Workspace で貢献度分析を使用する権限を付与します。 |
| **ダッシュボードの項目** |  |
| ダッシュボード項目の設定を使用すると、Reports &amp; Analytics の[レポートレット](https://docs.adobe.com/content/help/ja-JP/analytics/admin/server-call-usage/server-call-usage-dashboard.html)（推奨レポート、会社サマリレポートレット、画像、KPI／ゲージレポートレット、レポートスイートの合計、テキスト、レポートレット、使用状況サマリレポートレット、Web リソースのレポートレット）にアクセスできます。 |  |
| **その他** |  |
| Social | Report Suite Manager のソーシャルの管理メニューへのアクセスを制御します。 |
