---
title: prop
description: レポートで使用できるカスタムディメンションです。
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
TQID: https://experienceleague.adobe.com/2WMG5X3GNmogf-9Bbapq78pjVg5ibQQw7Bgb0qNpF1E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 82%
---
# prop

>[!BEGINSHADEBOX]

*このヘルプページでは、propが[ ディメンション ](overview.md)として機能する仕組みについて説明します。 prop の実装方法について詳しくは、『実装ユーザーガイド』の [prop](/help/implement/vars/page-vars/prop.md) を参照してください。*

>[!ENDSHADEBOX]

prop は、任意の用途に使用できるカスタム変数です。 prop は、設定されたヒットの後は保持されません。

>[!TIP]
>
>ほとんどの場合、[eVar](evar.md) の使用をお勧めします。 以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。 ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)がある場合、これらのカスタムディメンションを組織に固有の値に割り当てることができます。 使用可能な prop の数は、アドビとの契約によって異なります。 アドビとの契約でサポートされている場合は、最大 75 個の prop を使用できます。

## データの prop への入力

各propは、AppMeasurementの対応する[`prop1` - `prop75`](/help/implement/vars/page-vars/prop.md)変数を使用してデータを収集します。 例えば、`prop1`変数はprop1 ディメンションに入力し、`prop68`変数はprop68 ディメンションに入力します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`prop1` - `prop75`](/help/implement/vars/page-vars/prop.md) |
| **Web SDK / XDM フィールド** | [`_experience.analytics.customDimensions.props.prop1` - `prop75`](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) |
| **クエリパラメーター** | [`c1` - `c75`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<prop1>` - `<prop75>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 100 バイト |
| **永続性** | ヒット |

## ディメンション項目

prop は実装にカスタム文字列を含むので、組織で各 prop のディメンション項目を決定します。 各propおよび一般的なディメンション項目の目的を[ ソリューション設計ドキュメント ](/help/implement/prepare/solution-design.md)に記録してください。

## 大文字と小文字の区別

prop は、デフォルトでは大文字と小文字が区別されません。 大文字と小文字で同じ値を送信する（`"DOG"` と `"Dog"` など）と、Analysis Workspace はそれらを同じディメンション項目にグループ化します。 レポート月の開始時に最初に観測された値の大文字と小文字が使用されます。 Data Warehouse では、リクエスト期間中に最初に発生した値が表示されます。

prop は大文字と小文字を区別するように設定することができます。 また、任意の prop を有効にした後、大文字と小文字の区別を無効にすることもできます。 大文字と小文字の区別を切り替えるには、レポートスイート ID と希望する変数を記載して、アドビカスタマーケアに連絡してください。

>[!WARNING]
>
>大文字と小文字の区別を切り替えると、ディメンション項目が分断され、セグメントで予期しない結果が生じたり、フィルターに問題が発生したりする場合があります。 この設定は、月や年の初めなどの区切りの良いタイミングで切り替えることを強くお勧めします。

## eVar と比較した prop の利点

ほとんどの場合、eVar の使用をお勧めします。 ただし、以下のような例外があります。

* prop はリアルタイムレポートで使用できます。 eVar はレポートに表示されるまでに 30 分以上かかります。
* prop はリスト prop になる機能があり、同じヒットで複数の値を受け入れます。 リスト変数は別の変数で、使用できるリスト変数は 3 つだけです。
* prop の場合、パスを有効にすると、[入口](entry-dimensions.md)ディメンションと[出口](exit-dimensions.md)ディメンションがすぐに使用可能になります。 eVar の入口ディメンションと離脱ディメンションが必要な場合は、セグメントを手動で作成できます。

prop と eVar の比較について詳しくは、[eVar](evar.md) を参照してください。
