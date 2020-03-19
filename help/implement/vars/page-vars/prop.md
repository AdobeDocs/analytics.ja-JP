---
title: prop
description: 実装で使用できるカスタム変数。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# prop

propは、好きなように使用できるカスタム変数です。

> [!TIP] ほとんどの場合、eVarの使用をお勧めします。 以前のバージョンのAdobe Analyticsでは、propとeVarは互いに利点と欠点を持っていました。 ただし、アドビではeVarを改善し、propのほとんどすべての使用例を満たすようにしました。 これらの [2つのカスタム変数型の機能の比較については、eVars](evar.md) (eVar)を参照してください。

組織でpropを使用する場合は、使用とロジックを必ずソリューションデザインドキュメントに記 [録してください](../../prepare/solution-design.md)。

## Adobe Experience Platform Launchのprop

propは、Analytics拡張の設定時（グローバル変数）またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Props] section.

propを選択して、値またはデータ要素を設定できます。 別のAnalytics変数から値をコピーすることもできます。

## AppMeasurementのs.prop1 ～ s.prop75と、カスタムコードエディターの起動

各prop変数は、組織固有のカスタム値を含む文字列です。 最大長は100バイトです。100バイトを超える値は、アドビに送信されると自動的に切り捨てられます。

```js
s.prop1 = "Example custom value";
```

## リストprop

リストpropは、変数が同じヒット内の複数の値を保持できるように、propに適用される設定です。 この設定が有効でない場合、または誤った区切り文字が使用された場合、変数は単一の値として扱われます。

### リストpropの設定

レポートスイートの設定でリストpropを有効にします。 See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. 目的の区切り文字が正しく設定されていることを確認します。 デフォルトの区切り文字は提供されません。

> [!TIP] 実装で使用される一般的な区切り文字は、`,`コンマ()、コ`:`ロン()、セミコ`;`ロン()またはパイプ(`|`)です。 実装に最適な任意の区切り文字を使用できます。

### リストpropの設定

レポートスイートの設定で目的の区切り文字を使用してリストpropを設定した後は、区切り文字を使用する以外に実装上の違いはありません。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] リストpropは、引き続き最大長100バイトの影響を受けます。 リストpropは複数の値を含む可能性があるので、この制限に達しやすく、切り捨てられます。 この100バイトの制限に達した場合は、省略形の使用や値の短縮を検討してください。

リストpropで同じ値を複数回設定した場合、レポートで重複が排除されます。 Analysis Workspaceは、値が表示されたヒット数をカウントし、値がデータに存在した回数はカウントしません。
