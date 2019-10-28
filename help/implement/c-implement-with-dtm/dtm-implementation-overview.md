---
description: 'null'
keywords: Analytics の実装, 実装方法, dynamic tag management, dtm
seo-description: 'null'
seo-title: DTM 実装の概要
solution: Analytics
title: DTM 実装の概要
topic: 開発者と実装
uuid: 2d40cb7a-5c69-4f41-81a7-c48373c2d720
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# DTM 実装の概要

Dynamic Tag Management を使用すると、タグを管理し、デジタルマーケティングシステム全体でデータを収集および配布できます。Dynamic Tag Management では、単一のデータ層で複数のソースのデータをプッシュできます。それぞれの顧客に適したコンテンツを提供することもできます。

この節では、Dynamic Tag Management を利用して Adobe Analytics を導入する方法について説明します。Dynamic Tag Management について詳しくは、「[Dynamic Tag Management 製品ドキュメント](https://marketing.adobe.com/resources/help/ja_JP/dtm/)」を参照してください。DTM の使用を開始する際の DTM へのアクセスと一般的なタスクについて詳しくは、「[はじめに](https://marketing.adobe.com/resources/help/ja_JP/dtm/get_started.html)」を参照してください。

Dynamic Tag Management の実装手順の詳細については、Adobe Analytics 使用の手引きの「[Dynamic Tag Management を使用した Adobe Analytics のデプロイ](https://marketing.adobe.com/resources/help/ja_JP/analytics/getting-started/add-adobe-analytics-dtm-tool.html)」を参照してください。

## 導入手順の概要 {#section_D0BBB82486F44699AC7FF5E76E27434C}

このガイドでは、DTM を使用して Analytics を導入する際の次の手順について説明します。

1. [Web プロパティを作成](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)する。
1. [ホスティングオプションを設定](../../implement/c-implement-with-dtm/t-configure-hosting.md#task_EAD99BB391F544C0BB197D0B3D03EBAC)する。
1. [各管理対象ページにヘッダーおよびフッターコードを追加](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5)する。
1. [Adobe Analytics ツールを追加](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8)する。
1. [データ要素](../../implement/c-implement-with-dtm/t-data-element.md#task_962EF08CE2AE49B3B739295F6E4792C2)、[ルールと条件](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB)、[アクション](../../implement/c-implement-with-dtm/c-rules/t-rules-actions.md#task_94DFE0D8B53A43E2892851BABE381121)を作成します。

1. 実稼動サーバーにツールおよびルールを発行する。

