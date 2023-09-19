---
description: Adobe Analytics が収集するデータの概要とプライバシーに関する他の考慮事項です。
keywords: プライバシー
title: プライバシーの概要
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 9fd055fd747c7124d49e280af1b0acc24d79be8e
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 3%

---

# プライバシーの概要

Adobeは、適用される法令に準拠できるように組織を有効にしたいと考えています。 詳しくは、 [Adobe Experience Cloudのプライバシー](https://www.adobe.com/jp/privacy/experience-cloud.html){target=_blank} を参照してください。 Adobe Analyticsと組織の間では、Adobeは「データ処理者」として機能し、お客様は「データ管理者」（または該当するプライバシーおよびデータ保護法に基づく同等の者）となります。 Adobeのソリューションの実装方法は組織によってのみ制御されるので、Adobeの製品およびサービスの使用方法を開示するかどうかは、組織次第です。 Adobe Analyticsを使用している間、組織は、お客様独自のプライバシーポリシー、お客様とAdobeとのサービス契約、およびすべての適用法に準拠する責任を負います。

Adobeでは、次の包括的な概念に従うことを強くお勧めします。

* **個人データを収集する場合は、プライバシーに関する法律や規制に従ってください。** カスタム変数を使用すると、ほぼすべての項目にアクセスできる情報を収集できますが、組織のプライバシーポリシーや適用法についても考慮する必要があります。
* **顧客に対し、組織のプライバシー情報を見つけやすく分かりやすく提供する。** オプトアウトリンク、参照データの使用方法、Adobeのサービスの使用方法や計画など、役立つ情報が含まれます。
* **お客様に適用される現地の法律と国際法の両方に注意してください。** 組織がグローバルな規模で運営する場合は、一部の国際法が適用される場合があります。

## データ収集の分類

Adobeは、データをAdobeに送信する際に役立つ、複数のデータ収集ライブラリを提供します。 主な例を次に示します。

* **AppMeasurement**：データをAdobe Analyticsに直接送信するように設計されたライブラリ。
* **Web SDK**：データをAdobe Experience Platform Edge ネットワークに送信するように設計されたライブラリです。このライブラリは、そのデータをAdobe Analyticsに転送します。
* **タグ**：最初のタグ実装以外で、Web サイトやアプリのソースコードにアクセスすることなく、実装を設定できる Web ベースの UI。 拡張機能は、AppMeasurementと Web SDK の両方で使用できます。

Adobe Analyticsでは、次のタイプのデータを収集できます。

| データのタイプ | 詳細 | このデータを含む変数の例 |
| --- | --- | --- |
| サイト上の Web ページのページ名または URL | このデータは、Adobe Analyticsが機能するために必要です。 各ヒットには URL またはページ名が必要です。 | [ページ](../components/dimensions/page.md), [ページ URL](../components/dimensions/page-url.md) |
| 時間ベースのデータ | このデータは、Adobe Analyticsが機能するために必要です。 データ収集にはタイムスタンプが必要で、時間に基づくデータはタイムスタンプから取得されます。 | [ページでの滞在時間](../components/dimensions/time-spent-on-page.md), [時刻](../components/dimensions/hour-of-day.md), [午前/午後](../components/dimensions/am-pm.md), [平日/週末](../components/dimensions/weekday-weekend.md), [曜日](../components/dimensions/day-of-week.md), [月（年）](../components/dimensions/month-of-year.md) |
| リファラーデータ | データ収集ライブラリは、訪問者が Web サイトに到達したときに、デフォルトで参照 URL を収集します。 リファラーのクエリ文字列内のデータを収集するように実装をカスタマイズできます。 この方法は、キャンペーンおよび広告パフォーマンスのトラッキングで一般的です。 | [リファラー](../components/dimensions/referrer.md), [参照ドメイン](../components/dimensions/referring-domain.md) |
| 匿名化された訪問者 ID | データ収集ライブラリは、サイトを訪問する各ブラウザーの訪問者 ID を生成し、参照します。 この ID は Cookie に保存されます。 データ収集ライブラリで cookie 識別子を設定できない場合、そのライブラリでは匿名の訪問者識別のフォールバック方法が使用されます。 この方法では、訪問者の IP アドレスとユーザーエージェント文字列を使用して、関連するヒットを同じ訪問に結び付けます。 組織で IP の不明化が有効になっている場合、この設定は有効になりません。 詳しくは、 [Adobe Analyticsとブラウザーの cookie](cookies/cookies.md) を参照してください。 | [ユニーク訪問者](../components/metrics/unique-visitors.md) |
| 識別可能な訪問者 ID | Adobeは、カスタム訪問者 ID を自動的に収集しません。 ただし、このデータを収集するように実装をカスタマイズすることはできます。 | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| 外部検索用語 | 外部検索データには、検索エンジンから派生するキーワードが含まれます。 データ収集ライブラリは、参照 URL に基づいてこのデータを検索します。 ただし、多くの最新の検索エンジンでは、この情報は含まれていません。 | [検索キーワード](../components/dimensions/search-keyword.md) |
| 内部検索用語 | 内部検索データには、Web サイト内またはアプリの検索機能内から派生するキーワードが含まれます。 Adobeは、内部検索データを自動的に収集しません。 ただし、このデータを収集するように実装をカスタマイズすることはできます。 この方法は、Adobe Analyticsを使用する組織で一般的です。 | [eVar](../components/dimensions/evar.md) |
| コンピューターおよびブラウザーの仕様 | データ収集ライブラリは、ブラウザーの種類、オペレーティングシステムの種類、デバイスがデスクトップかモバイルの場合など、低エントロピーのブラウザーヒントを自動的に収集します。 ブラウザーの特定のバージョン/ビルド、デバイスモデル、オペレーティングシステムのバージョンなど、高エントロピーのヒントを収集するには、カスタム設定が必要です。 詳しくは、 [クライアントヒントの概要](client-hints.md) を参照してください。 | [ブラウザー](../components/dimensions/browser.md), [オペレーティングシステム](../components/dimensions/operating-systems.md), [モバイルディメンション](../components/dimensions/mobile-dimensions.md), [画面の解像度](../components/dimensions/monitor-resolution.md) |
| 位置情報 | Adobeには、（レポートスイートレベルで）各 Web サイトまたはアプリの位置情報データの収集を有効または無効にする機能が用意されています。 位置情報データ収集は、デフォルトで有効になっています。 | [市区町村](../components/dimensions/cities.md), [地域](../components/dimensions/regions.md), [国](../components/dimensions/countries.md) |
| IP アドレス | Adobeは、訪問者がこのデータを保存する際に、最後のオクテットを難読化するか、訪問者の IP アドレスを完全に難読化する機能を提供します。 通常、EMEA のお客様は、デフォルトで完全に不明化された IP アドレス設定をお持ちです。 難読化の設定に関係なく、IP アドレスはAdobe Analyticsではディメンションとして使用できず、 [データフィード](../export/analytics-data-feed/data-feed-overview.md). | なし |
| サイトで提供されたフォーム情報 | すべての実装タイプで、このデータを収集するために設定が必要です。 このデータは、カスタム変数に含めることができます。 | [eVar](../components/dimensions/evar.md) |
| サイト上で広告またはリンクをクリックしました | データ収集ライブラリを使用する場合は、デフォルトで収集されます。 「Activity Map」を有効にした場合は、クリックの場所などの追加情報を使用できます。 | [Activity Map](../analyze/activity-map/activity-map.md), [出口リンク](../components/dimensions/exit-link.md), [ダウンロードリンク](../components/dimensions/download-link.md) |
| サイトで購入した製品 | すべての実装タイプで、このデータを収集するために設定が必要です。 Adobeは、この情報を収集するためのデフォルトの変数をいくつか提供します。 | [製品](../components/dimensions/product.md), [購入回数](../components/metrics/orders.md), [売上高](../components/metrics/revenue.md) |

{style="table-layout:auto"}

のナビゲーションメニューを参照してください。 [Dimensionの概要](../components/dimensions/overview.md) および [指標の概要](../components/metrics/overview.md) を参照してください。

## データ処理の場所

Adobeでは、Adobe Analyticsのデータ処理場所が 3 つあります。 これらのサイトは生データを受け取り、レポートスイートに処理します。レポートスイートは、データの保存とレポートの取得に最適化されています。 これらのデータ処理場所は、米国（オレゴン）、英国（ロンドン）、シンガポールに存在します。 詳しくは、 [Adobe Analytics security の概要](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} を参照してください。
