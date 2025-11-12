---
description: Analytics とAudience Managerは、両方ともセグメントを使用します。 ただし、Analytics セグメントは、Audience Manager セグメントと完全には同じではありません。 これらの違いは、Analytics とAudience Managerのレポートに表示される不一致に一因となっています。 その結果、これらのソリューションの両方でセグメントの使用を開始する際に、これらの違いを試して理解することが重要かつ有用です。
title: Analytics と Audience Manager のセグメントについて
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 9%

---

# Analytics と Audience Manager のセグメントについて

Analytics とAudience Managerは、両方ともセグメントを使用します。 ただし、Analytics セグメントは、Audience Manager セグメントと完全には同じではありません。 これらの違いは、Analytics とAudience Managerのレポートに表示される不一致に一因となっています。 その結果、これらのソリューションの両方でセグメントの使用を開始する際に、これらの違いを試して理解することが重要かつ有用です。

## Audience Manager セグメント {#aam-segments}

Audience Manager セグメントは、論理ルールで結合された一連の定義済み特性の対象となる訪問者（ユーザー ID）のグループです。 訪問者（ユーザー ID）がAudience Managerのセグメントに含まれるかどうかを判断する条件は、次の 4 つです。

* ルールは、セグメント自体と、各セグメントを構成する特性に対して設定されます。 これらのルールは、ユーザー ID がセグメントの資格を得るために満たす必要がある、または示す必要がある条件を定義します。
* アルゴリズムモデリング。特定のセグメントに適合するユーザーは、アルゴリズムモデリングと分析に基づいて他のセグメントに適合する場合があります。
* 有効期間（TTL）の間隔。 セグメントメンバーシップは、設定された間隔の後に期限切れになるか、無期限に継続される可能性があります。
* 最新性と頻度。 ユーザーにインタラクション（特性の実現）があるタイミングと頻度を定義することは、サイト、セクション、または特定のクリエイティブに対する実際の（または認識された）関心レベルに基づいてセグメントを作成するのに役立ちます。

Audience Manager セグメントのメンバーシップは流動的です。 ユーザーは、現在の時点でセグメント条件に適合しているかどうかに応じて、セグメントにエントリしたり、セグメントからドロップアウトしたりできます。 つまり、Audience Manager セグメントの母集団は、時間の経過と共に増減する可能性があります。

Audience Manager セグメントは、Analytics ではオーディエンスとして示されます。

詳しくは、[&#x200B; セグメントビルダーにおける特性とセグメントの母集団データ &#x200B;](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=ja)、[&#x200B; シグナル、特性、セグメント &#x200B;](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=ja) を参照してください。

## Analytics セグメント {#analytics-segments}

Analytics セグメントは、レポート内のデータのフィルタリングメカニズムです。 フィルタリングは、Audience Manager のように訪問者レベルのみではなく、訪問者、訪問またはヒットのレベルでおこなうことができます。Analytics セグメントとAudience Manager セグメントを比較する際に考慮すべき重要な要因はいくつかあります。

* Analytics セグメントは、Audience Manager セグメントとは異なるデータセットに対して動作します。 Analytics は、データ収集時に、Audience Managerで使用できない様々な後処理手順をデータに適用します。 後処理には、eVarの永続性、処理ルール、ルックアップ（位置情報、モバイルデバイス）、VISTA など、様々なものが含まれます。 Audience Managerは、事前に処理されたデータをサーバーサイド転送（またはDIL）で受け取ります。

  Audience Managerでは、Analytics 内で有効期限のないディメンションに基づくセグメントと同じディメンションに基づくセグメントを比較すると、一般的なデータの不一致が発生します。 例えば、listVar や、有効期限切れにならないマーチャンダイジング eVar などです。

  例えば、eVar = blue で、期限切れになることがないと Analytics で設定されている場合、条件「eVar = blue」を持つ Analytics のセグメントには常にこの訪問者が含まれます。一方、Audience Managerでは、その訪問者は、設定された期間の後に、同様に定義されたセグメントから離脱する可能性があります。

* Analytics セグメントには、Adobe Audience Manager セグメントよりも多くの機能があります。 Audience Manager セグメントは常に訪問者レベルで評価されます。 Analytics セグメントは、訪問者、訪問、ヒットレベル（またはこれらのレベルの組み合わせ）で定義できます。 さらに、Analytics では、Audience Managerではサポートしていない高度なセグメント化機能（順次セグメント化など）をサポートしています。

* 前述のように、Audience Managerの訪問者は、現在の時点でセグメント条件に適合しているかどうかに応じて、セグメントにエントリしたりセグメントからドロップアウトしたりできます。

  逆に Analytics では、訪問者は、レポートの日付範囲に基づいてセグメントに含まれるかセグメントから除外されます。 例えば、先月 1 人の訪問者が購入を行ったとします。 Adobe Audience Managerでは、その訪問者は、日付範囲に関係なく、「購入者」セグメントに含まれます。 Analytics では、今月に基づくレポートには、セグメントに訪問者は含まれません。 ただし、今月と先月に基づくレポートには、セグメントに訪問者が含まれます。

詳しくは、[Analytics セグメントガイド &#x200B;](/help/components/segmentation/seg-home.md) を参照してください。
