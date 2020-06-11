---
title: prop
description: レポートで使用できるカスタムディメンション。
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 26%

---


# prop

*このヘルプページでは、propがディメンションとして機能する方法を説明します。 propの実装方法について詳しくは、『実装ユーザーガイド[](/help/implement/vars/page-vars/prop.md)』のpropsを参照してください。*

Prop は、好きなだけ使用できるカスタム変数です。設定されたヒットを超えては持続しません。

> [!TIP][ ほとんどの場合、eVar の使用をお勧めします。](evar.md)以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

ソリューションデザイン [ドキュメントがある場合](/help/implement/prepare/solution-design.md)、これらのカスタムディメンションを組織に固有の値に割り当てることができます。 使用可能なpropの数は、アドビとの契約によって異なります。 アドビとの契約でサポートされている場合は、最大75個のpropを使用できます。

## データをpropに入力する

各propは、イメージリクエストの [`c1` - `c75` クエリ文字列](/help/implement/validate/query-parameters.md) からデータを収集します。 例えば、 `c1` クエリ文字列パラメーターでprop1のデータを収集し、 `c68` クエリ文字列パラメーターでprop68のデータを収集します。

JavaScript変数をデータ収集用のイメージリクエストにコンパイルするAppMeasurementでは、変数 `prop1` — を使用 `prop75`します。 導入のガイドラインについては、『導入ユーザガイド』の [prop](/help/implement/vars/page-vars/prop.md) を参照してください。

## 分析コード値

propは実装にカスタム文字列を含むので、組織は各propのディメンション値を決定します。 各propの目的と一般的なディメンション値を必ず [ソリューションデザインドキュメントに記録してください](/help/implement/prepare/solution-design.md)。

## eVarに対するpropの値

 ほとんどの場合、eVar の使用をお勧めします。この文の例外は次のとおりです。

* リアルタイムレポートでpropを使用できます。 eVarがレポートに表示されるまでに30分以上かかります。
* prop はリスト prop になる機能があり、同じヒットで複数の値を受け入れます。リスト変数は別の変数で、使用できるリスト変数は 3 つだけです。
* propでパスを有効にすると、 [入口](entry-dimensions.md) ディメンションと出 [](exit-dimensions.md) 口ディメンションがすぐに使用可能になります。 eVarの入口ディメンションと出口ディメンションが必要な場合は、セグメントを手動で作成できます。

propとeVarの比較について詳し [くは、eVar](evar.md) を参照してください。
