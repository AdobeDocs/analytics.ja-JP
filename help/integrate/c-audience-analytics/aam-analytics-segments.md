---
description: Analytics と Audience Manager ではセグメントが使用されます。ただし、Analytics セグメントは Audience Manager セグメントとまったく同じではありません。これらの相違は、Analytics レポートと Audience Manager レポートの相違に一部関係しています。このため、これらのソリューションでセグメントの操作を開始するときには、そうした相違を理解することが重要であり、役に立ちます。
seo-description: Analytics と Audience Manager ではセグメントが使用されます。ただし、Analytics セグメントは Audience Manager セグメントとまったく同じではありません。これらの相違は、Analytics レポートと Audience Manager レポートの相違に一部関係しています。このため、これらのソリューションでセグメントの操作を開始するときには、そうした相違を理解することが重要であり、役に立ちます。
seo-title: AnalyticsおよびAudience Managerのセグメントの理解
title: AnalyticsおよびAudience Managerのセグメントの理解
uuid: 13f7d1d7-6a3f-42f1-822e-8d3523999efa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# AnalyticsおよびAudience Managerのセグメントの理解

Analytics と Audience Manager ではセグメントが使用されます。ただし、Analytics セグメントは Audience Manager セグメントとまったく同じではありません。これらの相違は、Analytics レポートと Audience Manager レポートの相違に一部関係しています。このため、これらのソリューションでセグメントの操作を開始するときには、そうした相違を理解することが重要であり、役に立ちます。

## Audience Manager セグメント {#section_417DC4B5648547778A27E42CE1D09900}

Audience Manager セグメントは、論理的なルールによって結合され定義された一連の特性に合致する訪問者（ユーザー ID）のグループです。訪問者（ユーザー ID）が Audience Manager セグメントの一部であるかどうかを判別する 4 つの条件があります。

* セグメント自体に設定されているルール、および各セグメントを形成する特性。これらのルールは、ユーザー ID がセグメントに認定されるために満たす必要のある条件を定義します。
* アルゴリズムモデリング。特定のセグメントに認定されているユーザーは、アルゴリズムモデリングと分析に基づいて別のセグメントにも認定される場合があります。
* Time-to-live（TTL）の間隔。セグメントのメンバーシップは、設定された間隔の後に期限切れになるか、無期限で継続されます。
* 最新性と頻度。ユーザーインタラクションがいつ、どのくらいの頻度でおこなわれているかを定義する（特性の具現化）と、サイト、セクション、特定のクリエイティブに対する実際の（または認識された）関心レベルに基づいてセグメントを作成できます。

Audience Manager セグメントのメンバーシップは流動的です。ユーザーは、現時点でセグメントの条件を満たしているかどうかに応じて、セグメントに含められたり、除外されたりします。これは、Audience Manager セグメントの母集団が時間の経過に従って増減することがあることを意味します。

Audience Manager セグメントは、Analytics ではオーディエンスとして示されます。

詳しくは、[セグメントビルダーの特性とセグメント母集団データ](https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html)および[シグナル、特性およびセグメント](https://marketing.adobe.com/resources/help/en_US/aam/c_signal_trait_segment.html)を参照してください。

## Analytics セグメント {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Analytics セグメントは、レポートのデータのフィルタリングメカニズムです。フィルターは、訪問者レベルではなく、訪問者レベル、訪問レベルまたはヒットレベルで発生する可能性があります。Analytics セグメントと Audience Manager セグメントを比較するときに考慮する必要があるいくつかの重要な要因があります。

* Analytics セグメントは、Audience Manager セグメントとは異なる一連のデータに作用します。データ収集中に、Analytics は Audience Manager ではおこなわれない様々な後処理をデータに適用します。後処理には、eVar の持続性、処理ルール、参照（位置情報、モバイルデバイス）、VISTA などがあります。Audience Manager は、前処理されたデータをサーバー側転送（または DIL）から受け取ります。

   一般的に、データの相違は、期限切れになることがない Analytics のディメンションと Audience Manager の同じディメンションに基づいてセグメントを比較したときに発生します。例えば、期限切れになることがない listVars またはマーチャンダイジング eVar です。

   例えば、eVar = blue で、期限切れになることがないと Analytics で設定されている場合、条件「eVar = blue」を持つ Analytics のセグメントには常にこの訪問者が含まれます。それに対して、Audience Manager では、設定された期間の後に、同様に定義されたセグメントからその訪問者が除外される場合があります。

* Analytics セグメントには AAM セグメントより多くの機能があります。Audience Manager セグメントは、常に訪問者レベルで評価されます。Analytics セグメントは、訪問者、訪問またはヒットのレベル（またはこれらのレベルの組み合わせ）で定義できます。また、Analytics では、Audience Manager ではサポートされない連続セグメントなどの拡張セグメント機能がサポートされます。
* 前述のように、Audience Manager の訪問者は、現時点でセグメントの条件を満たしているかどうかに応じてセグメントに含められたり、除外されたりします。

   逆に、Analytics では、訪問者はレポートの日付範囲に基づいてセグメントに含められたり、除外されたりします。例えば、1 人の訪問者が先月購入をおこなったとします。AAM では、その訪問者は日付範囲に関係なく「購入者」セグメントに含められます。Analytics の今月に基づくレポートでは、この訪問者は「購入者」セグメントに含められません。しかし、今月と先月に基づくレポートではこの訪問者が「購入者」セグメントに含められます。

詳しくは、[Analytics セグメントガイド](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)を参照してください。
