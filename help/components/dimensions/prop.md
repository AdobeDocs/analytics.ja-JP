---
title: prop
description: レポートで使用できるカスタムディメンションです。
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
TQID: https://experienceleague.adobe.com/2WMG5X3GNmogf-9Bbapq78pjVg5ibQQw7Bgb0qNpF1E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 475
ht-degree: 93%

---

# prop

*このヘルプページでは、propが[ ディメンション ](overview.md)として機能する仕組みについて説明します。 prop の実装方法について詳しくは、『実装ユーザーガイド』の [prop](/help/implement/vars/page-vars/prop.md) を参照してください。*

prop は、好きなだけ使用できるカスタム変数です。 prop は、設定されたヒットの後は保持されません。

>[!TIP]
>
>ほとんどの場合、[eVar](evar.md) の使用をお勧めします。 以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。 ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)がある場合、これらのカスタムディメンションを組織に固有の値に割り当てることができます。 使用可能な prop の数は、アドビとの契約によって異なります。 アドビとの契約でサポートされている場合は、最大 75 個の prop を使用できます。

## データの prop への入力

各 prop は、イメージリクエストの [`c1` - `c75`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを収集します。 例えば、`c1` クエリ文字列パラメーターで prop1 のデータを収集し、`c68` クエリ文字列パラメーターで prop68 のデータを収集します。

JavaScript 変数をデータ収集用のイメージリクエストにコンパイルする AppMeasurement では、変数 `prop1` — `prop75` を使用します。 実装のガイドラインについては、『実装ユーザーガイド』の [prop](/help/implement/vars/page-vars/prop.md) を参照してください。

## ディメンション項目

prop は実装にカスタム文字列を含むので、組織で各 prop のディメンション項目を決定します。 各propおよび一般的なディメンション項目の目的を[ ソリューション設計ドキュメント ](/help/implement/prepare/solution-design.md)に記録してください。

## 大文字と小文字の区別

prop は、デフォルトでは大文字と小文字が区別されません。 大文字と小文字で同じ値を送信する（`"DOG"` と `"Dog"` など）と、Analysis Workspace はそれらを同じディメンション項目にグループ化します。 その場合、ディメンション項目に表示されるのは、レポートする月の最初に表示される最初の値の文字列です。 Data Warehouse では、リクエスト期間中に最初に発生した値が表示されます。

prop は大文字と小文字を区別するように設定することができます。 また、任意の prop を有効にした後、大文字と小文字の区別を無効にすることもできます。 大文字と小文字の区別を切り替えるには、レポートスイート ID と目的の変数をアドビカスタマーケアに連絡します。

>[!WARNING]
>
>大文字と小文字の区別を切り替えると、ディメンション項目の切り替え、セグメントでの予期しない結果の発生、フィルターの問題の原因となる場合があります。 この設定は、月や年の初めなどの区切りの良いタイミングで切り替えることを強くお勧めします。

## eVar と比較した prop の利点

ほとんどの場合、eVar の使用をお勧めします。 ただし、以下のような例外があります。

* prop はリアルタイムレポートで使用できます。 eVar はレポートに表示されるまでに 30 分以上かかります。
* prop はリスト prop になる機能があり、同じヒットで複数の値を受け入れます。 リスト変数は別の変数で、使用できるリスト変数は 3 つだけです。
* prop の場合、パスを有効にすると、[入口](entry-dimensions.md)ディメンションと[出口](exit-dimensions.md)ディメンションがすぐに使用可能になります。 eVar の場合、入口ディメンションと出口ディメンションが必要な場合は、セグメントを手動で作成します。

prop と eVar の比較について詳しくは、[eVar](evar.md) を参照してください。
