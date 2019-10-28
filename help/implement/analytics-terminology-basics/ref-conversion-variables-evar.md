---
description: カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。
keywords: Analytics の実装, eVar, コンバージョン変数, eVar 値, コンバージョン, 成功イベント
seo-description: カスタムインサイトコンバージョン変数（または eVar）は、サイト上の選択された Web ページの Adobe コードに配置されます。その主な目的は、カスタムマーケティングレポートでコンバージョン成功指標をセグメント化することです。
seo-title: コンバージョン変数（eVar）
solution: Analytics
title: コンバージョン変数（eVar）
topic: 開発者と実装
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: ht
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
>Analytics の導入時は、どの eVar をどのくらい使用するかを把握することが重要です。それらの eVar を Admin Console で設定する方法を把握する必要もあります。eVar について詳しくは、Analytics ヘルプおよびリファレンス ドキュメントの「[コンバージョン変数（eVar）](https://marketing.adobe.com/resources/help/ja_JP/reference/conversion_var_admin.html)」を参照してください。

eVar は訪問ベースにすることができ、cookie と同じように機能します。eVar 変数に渡された値は、事前設定した期間、ユーザーを追跡します。

1 つの eVar を 1 人の訪問者の値に設定すると、その値が期限切れになるまで自動的に記憶されます。eVar 値がアクティブなときに訪問者に対して発生したすべての成功イベントは、その eVar 値にカウントされます。

>[!NOTE]
>
>イメージリクエストの 1 つの eVar には、単一の値のみを格納できます。1 つの eVar の値に複数の値を格納したい場合は、[](/help/implement/js-implementation/c-variables/page-variables.md)リスト変数（リスト var）を実装することをお勧めします。

変数について詳しくは、以下を参照してください。

* このヘルプの「[Analytics の実装およびレポート用の変数](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB)」。
* [変数 - レポートでの使用方法](https://marketing.adobe.com/resources/help/ja_JP/reference/variable_definitions.html)
* [ページ変数](/help/implement/js-implementation/c-variables/page-variables.md)
* [キャンペーン変数](/help/implement/js-implementation/c-variables/page-variables.md)
* [products 変数](/help/implement/js-implementation/c-variables/page-variables.md)
* Mobile SDK ドキュメントの「[products 変数](https://marketing.adobe.com/resources/help/ja_JP/mobile/android/products.html)」。

