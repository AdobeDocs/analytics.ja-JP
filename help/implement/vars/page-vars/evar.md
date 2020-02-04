---
title: eVar
description: 実装で使用できるカスタム変数。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# eVar

eVarは、好きなだけ使用できるカスタム変数です。

> [!TIP] ほとんどの場合、propよりもeVarを使用することをお勧めします。 以前のバージョンのAdobe Analyticsでは、propとeVarは互いに利点と欠点がありました。 ただし、アドビではeVarを改善し、propのほとんどすべての使用例を満たすようにしました。

各eVarとそのロジックの使用方法を必ずソリューションデザインドキュメントに記 [録してください](../../prepare/solution-design.md)。

## レポートスイート設定でのeVarの設定

実装でeVarを使用する前に、各eVarをレポートスイートの設定で設定してください。 See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## Adobe Experience Platform LaunchのeVar

eVarは、Analytics拡張の設定時（グローバル変数）またはルールの下で設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. eVarsセクション [!UICONTROL を見つけます] 。

eVarを選択して、値またはデータ要素を設定できます。 別のAnalytics変数から値をコピーすることもできます。

## AppMeasurementおよび起動のカスタムコードエディターでのs.eVar1 ～ s.eVar250

各eVarは、組織に固有のカスタム値を含む文字列です。 最大長は255バイトです。255バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.eVar1 = "Example custom value";
```

## カウンター eVar

eVar値には通常、文字列値が含まれます。 ただし、eVarにカウンターを代わりに含めるように設定することはできます。 例えば、購入前に行われた内部検索の数をカウントするとします。 テキスト値を設定する代わりに、次の構文を使用します。

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

eVar カウンターで小数点以下が 3 桁以上ある場合は、2 桁に四捨五入されます。eVarカウンターに負の数を含めることはできません。

## propまたはeVarに対する排他的な利点

現在のバージョンのAdobe Analyticsでは、propとeVarは共通の機能を持つカスタム変数です。 ただし、主な違いはいくつかあります。

* propのデータは、数分以内にレポートで使用できます。 eVarがレポートに表示されるまでに30分以上かかる場合があります。
* レポートでは、propに100バイトの制限があります。 eVarには255バイトの制限があります。
* propはリストpropになる機能があり、同じヒットで複数の値を受け入れます。 リスト変数は別の変数で、使用できるリスト変数は3つだけです。
* デフォルトでは、propは設定されたヒットの後は保持されません。 eVarにはカスタムの有効期限があり、eVarがその後のイベントのクレジットを受け取らなくなった時期を判断できます。 レポートの時 [間処理を使用する場合](../../../components/vrs/vrs-report-time-processing.md)、propとeVarの両方で任意のアトリビューションモデルを使用できます。
