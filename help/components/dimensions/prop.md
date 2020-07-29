---
title: prop
description: レポートで使用できるカスタムディメンション。
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 19%

---


# prop

*このヘルプページでは、propがディメンションとして機能する方法を説明します。 For information on how to implement props, see[props](/help/implement/vars/page-vars/prop.md)in the Implement user guide.*

Prop は、好きなだけ使用できるカスタム変数です。設定されたヒットを超えては持続しません。

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. 以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

ソリューションデザイン [ドキュメントがある場合](/help/implement/prepare/solution-design.md)、これらのカスタムディメンションを組織に固有の値に割り当てることができます。 使用可能なpropの数は、Adobeとの契約によって異なります。 Adobeとの契約でサポートされている場合は、propは75個まで使用できます。

## データをpropに入力する

各propは、イメージリクエストの [`c1` - `c75` クエリ文字列](/help/implement/validate/query-parameters.md) からデータを収集します。 例えば、 `c1` クエリ文字列パラメーターでprop1のデータを収集し、 `c68` クエリ文字列パラメーターでprop68のデータを収集します。

JavaScript変数をデータ収集用のイメージリクエストにコンパイルするAppMeasurementでは、変数 `prop1` — を使用 `prop75`します。 導入のガイドラインについては、『導入ユーザガイド』の [prop](/help/implement/vars/page-vars/prop.md) を参照してください。

## Dimension項目

propは実装にカスタム文字列を含むので、組織は各propのディメンション項目を決定します。 各propと一般的なディメンション項目の目的を [ソリューションデザインドキュメントに記録してください](/help/implement/prepare/solution-design.md)。

## 大文字と小文字の区別

propは、デフォルトでは大文字と小文字が区別されません。 異なるケース( `"DOG"` となど)で同じ値を送信する場合、Analysis Workspaceはそれらを同じディメンション項目にグループ化し `"Dog"`ます。 レポートの月の最初に表示される最初の値の場合が使用されます。 Data warehouseには、リクエスト期間中に最初に発生した値が表示されます。

propでは大文字と小文字が区別されます。 また、任意のpropを有効にした後、大文字と小文字の区別を無効にすることもできます。 大文字と小文字の区別を切り替えるには、レポートスイートIDと目的の変数をAdobeカスタマーケアに連絡します。

>[!IMPORTANT]
>
>大文字と小文字の区別を切り替えると、ディメンション項目の切り替え、セグメントでの予期しない結果の発生、フィルターの問題の原因となる場合があります。 Adobeでは、この設定を月や年の初めなど、2つの主要な期間に切り替えることを強くお勧めします。

## eVarに対するpropの値

 ほとんどの場合、eVar の使用をお勧めします。この文の例外は次のとおりです。

* リアルタイムレポートでpropを使用できます。 eVarがレポートに表示されるまでに30分以上かかります。
* prop はリスト prop になる機能があり、同じヒットで複数の値を受け入れます。リスト変数は別の変数で、使用できるリスト変数は 3 つだけです。
* propでパスを有効にすると、 [入口](entry-dimensions.md) ディメンションと出 [](exit-dimensions.md) 口ディメンションがすぐに使用可能になります。 eVarの入口ディメンションと出口ディメンションが必要な場合は、セグメントを手動で作成できます。

propとeVarの比較について詳しくは、 [eVar](evar.md) を参照してください。
