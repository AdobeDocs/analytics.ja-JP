---
description: カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。
keywords: Analytics Implementation;eVar;conversion variable;eVar value;conversion;success event
title: コンバージョン変数（eVar）
topic: Developer and implementation
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# コンバージョン変数（eVar）

カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。

eVar は、次のような原因と結果を測定するために最適です。

* 売上に影響を与えた内部キャンペーン
* 最終的に登録につながったバナー広告
* 発注前に内部検索が使用された回数

>[!IMPORTANT]
>
>Analytics の導入時は、どの eVar をどのくらい使用するかを把握することが重要です。それらの eVar を Admin Console で設定する方法を把握する必要もあります。eVar について詳しくは、Analytics ヘルプとリファレンスの[コンバージョン変数（eVar）](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html)を参照してください。

eVar は訪問ベースにすることができ、cookie と同じように機能します。eVar 変数に渡された値は、事前設定した期間、ユーザーを追跡します。

1 つの eVar を 1 人の訪問者の値に設定すると、その値が期限切れになるまで自動的に記憶されます。eVar 値がアクティブなときに訪問者に対して発生したすべての成功イベントは、その eVar 値にカウントされます。

> [!NOTE]イメージリクエストの 1 つの eVar には、単一の値のみを格納できます。1 つの eVar の値に複数の値を格納したい場合は、[](/help/implement/js-implementation/page-variables/listvariable.md)リスト変数（リスト var）を実装することをお勧めします。

変数について詳しくは、以下を参照してください。

* このヘルプの「[Analytics の実装およびレポート用の変数](/help/implement/js-implementation/c-variables/sc-variables.md)」。
* [変数 - レポートでの使用方法](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [ページ変数](/help/implement/js-implementation/page-variables/page-variables.md)
* [キャンペーン変数](/help/implement/js-implementation/page-variables/campaign.md)
* [products 変数](/help/implement/js-implementation/page-variables/products.md)
* [products 変数](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html)（モバイル SDK のドキュメント）

