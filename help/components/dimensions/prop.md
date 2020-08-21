---
title: prop
description: レポートで使用できるカスタムディメンション。
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 63%

---


# prop

*このヘルプページでは、prop がディメンションとして機能するしくみについて説明します。prop の実装方法について詳しくは、『実装ユーザガイド』の[prop](/help/implement/vars/page-vars/prop.md)を参照してください。*

Prop は、好きなだけ使用できるカスタム変数です。Prop は、設定されたヒットの後は保持されません。

>[!TIP]
>
>ほとんどの場合、[eVar](evar.md) の使用をお勧めします。以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)がある場合、これらのカスタムディメンションを組織に固有の値に割り当てることができます。使用可能な prop の数は、アドビとの契約によって異なります。アドビとの契約でサポートされている場合は、最大 75 個の prop を使用できます。

## データの prop への入力

各 prop は、イメージリクエストの [`c1` - `c75`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを収集します。例えば、`c1` クエリー文字列パラメーターで prop1 のデータを収集し、`c68` クエリー文字列パラメーターで prop68 のデータを収集します。

JavaScript 変数をデータ収集用のイメージリクエストにコンパイルする AppMeasurement では、変数 `prop1` — `prop75` を使用します。実装のガイドラインについては、『実装ユーザガイド』の [prop](/help/implement/vars/page-vars/prop.md) を参照してください。

## Dimension項目

propは実装にカスタム文字列を含むので、組織は各propのディメンション項目を決定します。 Make sure you record the purpose of each prop and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).

## 大文字と小文字の区別

propは、デフォルトでは大文字と小文字が区別されません。 異なるケース( `"DOG"``"Dog"`となど)で同じ値を送信する場合、Analysis Workspaceはそれらを同じディメンション項目にグループ化します。 レポートの月の最初に表示される最初の値の場合が使用されます。 Data Warehouseには、リクエスト期間中に最初に発生した値が表示されます。

propでは大文字と小文字が区別されます。 また、任意のpropを有効にした後、大文字と小文字の区別を無効にすることもできます。 大文字と小文字の区別を切り替えるには、レポートスイートIDと目的の変数をAdobeカスタマーケアに連絡します。

>[!IMPORTANT]
>
>大文字と小文字の区別を切り替えると、ディメンション項目の切り替え、セグメントでの予期しない結果の発生、フィルターの問題の原因となる場合があります。 Adobeでは、この設定を月や年の初めなど、2つの主要な期間に切り替えることを強くお勧めします。

## eVar に対する prop の値

 ほとんどの場合、eVar の使用をお勧めします。この文の例外は次のとおりです。

* リアルタイムレポートで prop を使用できます。eVar がレポートに表示されるまでに 30 分以上かかります。
* prop はリスト prop になる機能があり、同じヒットで複数の値を受け入れます。リスト変数は別の変数で、使用できるリスト変数は 3 つだけです。
* Prop でパスを有効にすると、[入口](entry-dimensions.md)ディメンションと[出口](exit-dimensions.md)ディメンションがすぐに使用可能になります。eVar の入口ディメンションと出口ディメンションが必要な場合は、セグメントを手動で作成できます。

Prop と eVar の比較について詳しくは、[eVar](evar.md) を参照してください。
