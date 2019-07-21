---
description: カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。
keywords: Analyticsの導入;eVar;conversion variable;eVar値;コンバージョン;successイベント
seo-description: カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。
seo-title: コンバージョン変数（eVar）
solution: Analytics
title: コンバージョン変数（eVar）
topic: 開発者と導入
uuid: 50071c1c- be00-4b3a- a7ee-5d129conact498b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# コンバージョン変数（eVar）

カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。

eVar は、次のような原因と結果を測定するために最適です。

* 売上に影響を与えた内部キャンペーン
* 最終的に登録につながったバナー広告
* 発注前に内部検索が使用された回数

>[!IMPORTANT]
>
>Analyticsの導入時には、使用するeVarの数と、使用するeVarの数を把握することが重要です。それらの eVar を Admin Console で設定する方法を把握する必要もあります。eVar について詳しくは、Analytics ヘルプとリファレンスの[コンバージョン変数（eVar）](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html)を参照してください。

eVar は訪問ベースにすることができ、cookie と同じように機能します。eVar 変数に渡された値は、事前設定した期間、ユーザーを追跡します。

1 つの eVar を 1 人の訪問者の値に設定すると、その値が期限切れになるまで自動的に記憶されます。eVar 値がアクティブなときに訪問者に対して発生したすべての成功イベントは、その eVar 値にカウントされます。

>[!NOTE]
>
>イメージリクエストのeVarに格納できるのは単一の値のみです。1 つの eVar の値に複数の値を格納したい場合は、[](/help/implement/js-implementation/c-variables/page-variables.md)リスト変数（リスト var）を実装することをお勧めします。

変数について詳しくは、以下を参照してください。

* [Analytics導入およびこのヘルプのレポート](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) の変数
* [変数 - レポートでの使用方法](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [ページ変数](/help/implement/js-implementation/c-variables/page-variables.md)
* [キャンペーン変数](/help/implement/js-implementation/c-variables/page-variables.md)
* [products 変数](/help/implement/js-implementation/c-variables/page-variables.md)
* [products 変数](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html)（モバイル SDK のドキュメント）

