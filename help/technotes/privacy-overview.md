---
description: Adobe Analytics が収集するデータの概要とプライバシーに関する他の考慮事項です。
keywords: プライバシー
title: プライバシーの概要
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 12%

---

# プライバシーの概要

訪問者は[アドビプライバシーセンター](https://www.adobe.com/jp/privacy.html)にアクセスして、アドビが収集した情報の一般的な使用方法に関する詳細情報を入手できます。アドビのサービスの実装方法は貴社によってのみ管理されるので、アドビの製品とサービスの使用方法を開示するかどうかは、貴社に委ねられています。お客様の組織は、お客様独自のプライバシーポリシー、お客様とAdobeとのサービス契約、およびすべての適用法に準拠する責任を負います。

Adobeでは、次の包括的な概念に従うことを強くお勧めします。

* **Adobe Analyticsで個人を特定できる情報を収集しない。** カスタム変数を使用すると、ほぼすべての項目にアクセスできる情報を収集できますが、組織のプライバシーポリシーや適用法についても考慮する必要があります。
* **オプトアウト情報に関する情報を、訪問者が見つけやすく分かりやすく提供します。** 厳密に必要でないものをオプトアウトすることを許可します。 欧州連合には、分析 cookie を厳密に必要としていない国が多くあります。

## データ収集の分類

Adobe Analyticsは、自動的に次のタイプのデータを収集する、または収集する可能性があります。

| データのタイプ | 詳細 | このデータを含む変数の例 |
| --- | --- | --- |
| サイト上の Web ページのページ名または URL | 常に収集されます。 各ヒットには URL またはページ名が必要です。 | [ページ](../components/dimensions/page.md), [ページ URL](../components/dimensions/page-url.md) |
| 時間ベースのデータ | 常に収集されます。 データ収集にはタイムスタンプが必要で、時間に基づくデータはタイムスタンプから取得されます。 | [ページでの滞在時間](../components/dimensions/time-spent-on-page.md), [時刻](../components/dimensions/hour-of-day.md), [午前/午後](../components/dimensions/am-pm.md), [平日/週末](../components/dimensions/weekday-weekend.md), [曜日](../components/dimensions/day-of-week.md), [月（年）](../components/dimensions/month-of-year.md) |
| 他のサイトの Web ページからのデータ | Adobeは、Web サイトのソースコードを変更できない非関連サイトのデータを収集できません。 AppMeasurementは、訪問者が Web サイトに到達すると、参照 URL を自動的に収集します。 実装をカスタマイズして、サイトに到達した後でクエリ文字列内のデータを収集できます。 | [リファラー](../components/dimensions/referrer.md), [参照ドメイン](../components/dimensions/referring-domain.md) |
| 匿名化された訪問者 ID | AppMeasurementは、サイトを訪問する各ブラウザーの訪問者 ID を自動的に生成して参照します。 この ID は Cookie に保存されます。 特定の実装で cookie が使用できない場合、Adobe Analyticsでは、IP アドレスとユーザーエージェント文字列を使用した、訪問者識別のフォールバック方法を使用します。 詳しくは、 [Adobe Analyticsとブラウザーの cookie](cookies/cookies.md) を参照してください。 | [ユニーク訪問者](../components/metrics/unique-visitors.md) |
| 識別可能な訪問者 ID | Adobeは、カスタム訪問者 ID を自動的に収集しません。ただし、このデータを収集するように実装をカスタマイズすることはできます。 | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| 外部検索用語 | AppMeasurementは、参照 URL に基づいて、このデータを自動的に収集しようとします。 ただし、多くの最新の検索エンジンでは、この情報は含まれていません。 | [検索キーワード](../components/dimensions/search-keyword.md) |
| 内部検索用語 | Adobeは、内部検索データを自動的に収集しません。 ただし、実装をカスタマイズしてこのデータを収集することはできるので、Adobe Analyticsを使用する組織では一般的な方法です。 | [eVar](../components/dimensions/evar.md) |
| コンピューターおよびブラウザーの仕様 | AppMeasurementは、ブラウザーの種類、オペレーティングシステムの種類、デバイスがデスクトップかモバイルの場合など、低エントロピーのブラウザーヒントを自動的に収集します。 ブラウザーの特定のバージョン/ビルド、デバイスモデル、オペレーティングシステムのバージョンなど、高エントロピーのヒントを収集するには、設定が必要です。 詳しくは、 [クライアントヒントの概要](client-hints.md) を参照してください。 | [ブラウザー](../components/dimensions/browser.md), [オペレーティングシステム](../components/dimensions/operating-systems.md), [モバイルディメンション](../components/dimensions/mobile-dimensions.md), [画面の解像度](../components/dimensions/monitor-resolution.md) |
| 位置情報 | Adobeには、（レポートスイートレベルで）各 Web サイトまたはアプリの位置情報データの収集を有効または無効にする機能が用意されています。 このデータは、AppMeasurementを含む多くの実装タイプで自動的に収集されます。 | [市区町村](../components/dimensions/cities.md), [地域](../components/dimensions/regions.md), [国](../components/dimensions/countries.md) |
| IP アドレス | Adobeは、このデータを保存する際に、最後のオクテットを難読化するか、訪問者の IP アドレスを完全に難読化する機能を提供します。 通常、EMEA のお客様の IP アドレスは、デフォルトで完全に隠されています。 IP アドレスは、Adobe Analyticsではディメンションとして使用できません。生データ ([データフィード](../export/analytics-data-feed/data-feed-overview.md)) をクリックします。 | なし |
| サイトで提供されたフォーム情報 | すべての実装タイプで、このデータを収集するために設定が必要です。 このデータは、カスタム変数に含めることができます。 | [eVar](../components/dimensions/evar.md) |
| サイト上でクリックされた広告またはリンク | APPMEASUREMENT: クリックの場所などの追加情報は、「Activity Map」が有効な場合に使用できます。 | [Activity Map](../analyze/activity-map/activity-map.md), [出口リンク](../components/dimensions/exit-link.md), [ダウンロードリンク](../components/dimensions/download-link.md) |
| サイトで購入した製品 | すべての実装タイプで、このデータを収集するために設定が必要です。 Adobeには、この情報を保存するためのデフォルトの変数がいくつか用意されています。 | [製品](../components/dimensions/product.md), [購入回数](../components/metrics/orders.md), [売上高](../components/metrics/revenue.md) |

{style="table-layout:auto"}

のナビゲーションメニューを参照してください。 [Dimensionの概要](../components/dimensions/overview.md) および [指標の概要](../components/metrics/overview.md) を参照してください。
