---
description: Adobe Analytics が収集するデータの概要とプライバシーに関する他の考慮事項です。
keywords: プライバシー
title: プライバシーの概要
feature: Data Governance
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 98%

---

# プライバシーの概要

アドビは、お客様の組織が適用される法律や規制に準拠できるように支援します。詳しくは、[Adobe Experience Cloudのプライバシー ](https://www.adobe.com/jp/privacy/experience-cloud.html){target=_blank} を参照してください。 Adobe Analytics とお客様の組織との間では、アドビが「データ処理者」として機能し、お客様は「データ管理者」（または適用されるプライバシーおよびデータ保護法に基づく同等の者）となります。アドビのソリューションの実装方法はお客様の組織が独占的に管理するので、アドビの製品とサービスの使用方法を開示するかどうかは、お客様の組織に委ねられています。Adobe Analytics を使用する際、お客様の組織は、独自のプライバシーポリシー、アドビとのサービス契約および適用されるすべての法律を遵守する責任があります。

アドビでは、次の包括的な概念に従うことを強くお勧めします。

* **個人データを収集する場合は、プライバシー法および規制に準拠していることを確認します。**&#x200B;カスタム変数を使用すると、アクセスできるデータはほとんどすべて収集できます。ただし、組織のプライバシーポリシーおよび適用される法律も考慮する必要があります。
* **お客様の組織のプライバシー情報を見つけやすく、理解しやすい形でお客様の顧客に提供します。**&#x200B;役立つ情報には、オプトアウトリンク、閲覧データの使用方法、アドビのサービスの使用方法や使用計画などが含まれます。
* **適用される現地の法律と国際法の両方に注意してください。**&#x200B;お客様の組織が世界規模で運営されている場合は、一部の国際法が適用される可能性があります。

## データ収集の分類

アドビでは、アドビへのデータ送信に役立つ複数のデータ収集ライブラリを提供しています。注目すべき例は次のとおりです。

* **AppMeasurement**：Adobe Analytics にデータを直接送信するように設計されたライブラリ。
* **Web SDK**：Adobe Experience Platform Edge Network にデータを送信し、そのデータを Adobe Analytics に転送するように設計されたライブラリ。
* **タグ**：最初のタグ実装以降、web サイトやアプリのソースコードにアクセスする必要がなく、実装を設定できる web ベースの UI。拡張機能は、AppMeasurementと Web SDK の両方で使用できます。

Adobe Analytics は、次のタイプのデータを収集できます。

| データのタイプ | 詳細 | このデータを含む変数の例 |
| --- | --- | --- |
| サイトの web ページのページ名または URL | このデータは、Adobe Analytics が機能するために必要です。すべてのヒットに URL またはページ名が必要です。 | [ページ](/help/components/dimensions/page.md)、[ページ URL](/help/components/dimensions/page-url.md) |
| 時間ベースのデータ | このデータは、Adobe Analytics が機能するために必要です。データ収集にはタイムスタンプが必要で、時間ベースのデータはタイムスタンプから派生します。 | [ページでの滞在時間](/help/components/dimensions/time-spent-on-page.md)、[時刻](/help/components/dimensions/hour-of-day.md)、[午前／午後](/help/components/dimensions/am-pm.md)、[平日／週末](/help/components/dimensions/weekday-weekend.md)、[曜日](/help/components/dimensions/day-of-week.md)、[月](/help/components/dimensions/month-of-year.md) |
| リファラーデータ | データ収集ライブラリは、訪問者が web サイトに到達すると、デフォルトで参照 URL を収集します。実装をカスタマイズして、リファラーのクエリ文字列内のデータを収集できます。これは、キャンペーンや広告パフォーマンスのトラッキングで一般的です。 | [リファラー](/help/components/dimensions/referrer.md)、[参照ドメイン](/help/components/dimensions/referring-domain.md) |
| 匿名化された訪問者 ID | データ収集ライブラリは、サイトにアクセスするブラウザーごとに訪問者 ID を生成して参照します。この ID は cookie に保存されます。データ収集ライブラリで cookie 識別子を設定できない場合、ライブラリでは匿名の訪問者を識別するフォールバックメソッドが使用されます。このメソッドでは、訪問者の IP アドレスとユーザーエージェント文字列を使用して、関連するヒットを同じ訪問に結び付けることが含まれます。お客様の組織で IP の不明化が有効になっている場合、この設定が適用されます。詳しくは、[Adobe Analytics とブラウザーの Cookie](../cookies/cookies.md) を参照してください。 | [ユニーク訪問者](/help/components/metrics/unique-visitors.md) |
| 識別可能な訪問者 ID | アドビは、カスタム訪問者 ID を自動的に収集しません。ただし、このデータを収集するように実装をカスタマイズできます。 | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| 外部検索語 | 外部検索データには、検索エンジンから生成されたキーワードが含まれます。データ収集ライブラリは、参照 URL に基づいてこのデータを検索します。ただし、最新の検索エンジンの多くには、この情報が含まれなくなりました。 | [検索キーワード](/help/components/dimensions/search-keyword.md) |
| 内部検索語 | 内部検索データには、web サイト内またはアプリの検索機能から生成されるキーワードが含まれます。アドビは、内部検索データを自動的に収集しません。ただし、このデータを収集するように実装をカスタマイズできます。この慣習は、Adobe Analytics を使用する組織では一般的です。 | [eVar](/help/components/dimensions/evar.md) |
| コンピューターとブラウザーの仕様 | データ収集ライブラリは、ブラウザーの種類、オペレーティングシステムの種類、デバイスがデスクトップかモバイルかなど、低エントロピーのブラウザーヒントを自動的に収集します。ブラウザーの特定のバージョン／ビルド、デバイスモデル、オペレーティングシステムのバージョンなど、高エントロピーのヒントを収集するには、カスタム設定が必要です。詳しくは、[クライアントヒントの概要](../client-hints.md)を参照してください。 | [ブラウザー](/help/components/dimensions/browser.md)、[オペレーティングシステム](/help/components/dimensions/operating-systems.md)、[モバイルディメンション](/help/components/dimensions/mobile-dimensions.md)、[画面の解像度](/help/components/dimensions/monitor-resolution.md) |
| ジオロケーション情報 | IP アドレスの最後のオクテットを 0 に設定することで、アドビは詳細な位置情報を防ぐ機能を提供しています。これにより、位置情報の精度が下がりますが、[レポートスイートの設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)で設定できます。 | [市](/help/components/dimensions/cities.md)、[地域](/help/components/dimensions/regions.md)、[国](/help/components/dimensions/countries.md) |
| IP アドレス | このデータを保存する際に、訪問者の IP アドレスを不明化（ハッシュ）したり、完全に削除したりできます。EMEA のお客様は通常、デフォルトで IP アドレス設定が不明化されています。不明化設定に関係なく、Analysis Workspace では IP アドレスをディメンションとして使用することはできません。[データフィード](/help/export/analytics-data-feed/data-feed-overview.md)にのみ含まれます。使用可能な不明化設定について詳しくは、管理者ガイドの[一般的なアカウント設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)を参照してください。 | なし |
| サイトで提供されるフォーム情報 | すべての実装タイプでは、このデータを収集するための設定が必要です。このデータをカスタム変数に含めることができます。 | [eVar](/help/components/dimensions/evar.md) |
| サイト上の広告またはリンクをクリックしました | [`trackExternalLinks`](/help/implement/vars/config-vars/trackexternallinks.md) または [`trackDownloadLinks`](/help/implement/vars/config-vars/trackdownloadlinks.md) が有効な場合に収集されます。Activity Map を有効にすると、クリックの場所などの追加情報を利用できます。 | [Activity Map](/help/analyze/activity-map/overview.md)、[離脱リンク](/help/components/dimensions/exit-link.md)、[ダウンロードリンク](/help/components/dimensions/download-link.md) |
| サイトで購入した製品 | すべての実装タイプでは、このデータを収集するための設定が必要です。アドビでは、この情報を収集するデフォルトの変数をいくつか用意しています。 | [製品](/help/components/dimensions/product.md)、[注文件数](/help/components/metrics/orders.md)、[収益](/help/components/metrics/revenue.md) |

{style="table-layout:auto"}

アドビがデータを収集できる可能性のあるその他の変数について詳しくは、[ディメンションの概要](/help/components/dimensions/overview.md)および[指標の概要](/help/components/metrics/overview.md)のナビゲーションメニューを参照してください。

## データ処理の場所

アドビでは、Adobe Analytics の 3 つのデータ処理場所を維持します。これらの Sites では、生データを受け取り、データストレージやレポート取得に最適化されたレポートスイートに処理します。これらのデータ処理の場所は、現在、米国（オレゴン）、英国（ロンドン）、シンガポールにあります。詳しくは、[Adobe Analytics セキュリティの概要 ](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} を参照してください。
