---
title: eVar
description: 実装で使用できるカスタム変数。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# eVar

*このヘルプページでは、eVarの実装方法を説明します。 eVarがディメンションとしてどのように機能するかについて詳しくは、コンポーネ[ントユーザ](../../../components/c-variables/dimensionslist/reports-conversion.md)ーガイドのeVarを参照してください。*

eVar は、好きなだけ使用できるカスタム変数です。

>[!TIP] ほとんどの場合、prop よりも eVar を使用することをお勧めします。以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

各 eVar とそのロジックの使用方法を必ず[ソリューションデザインドキュメント](../../prepare/solution-design.md)に記録してください。

## レポートスイート設定での eVar の設定

実装で eVar を使用する前に、各 eVar をレポートスイートの設定で設定してください。詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。

## Adobe Experience Platform Launch の eVar

eVar は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL eVars] section.

eVar を選択して、値またはデータ要素を設定できます。別の Analytics 変数から値をコピーすることもできます。

## AppMeasurement および Launch カスタムコードエディターの s.eVar1～s.eVar250

各 eVar は、組織に固有のカスタム値を含む文字列です。最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.eVar1 = "Example custom value";
```

## カウンター eVar

eVar 値には通常、文字列値が含まれます。ただし、eVar にカウンターを代わりに含めるように設定することはできます。例えば、購入前におこなわれた内部検索の数をカウントするとします。テキスト値を設定する代わりに、次の構文を使用します。

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

eVar カウンターで小数点以下が 3 桁以上ある場合は、2 桁に四捨五入されます。eVar カウンターには負の値は設定できません。

>[!IMPORTANT] カウンターeVarを使用する前に、管理コンソールでeVarを「カウンター」に設定する必要があります。 詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。

## prop または eVar 固有の利点

現在のバージョンの Adobe Analytics では、prop と eVar は共通の機能を持つカスタム変数です。ただし、主な違いはいくつかあります。

* prop のデータは、数分以内にレポートで使用できます。eVar はレポートスイートデータに表示されるまでに 30 分以上かる場合があります。
* レポートでは、prop に 100 バイトの上限があります。eVar の上限は 255 バイトです。
* prop はリスト prop になる機能があり、同じヒットで複数の値を受け入れます。リスト変数は別の変数で、使用できるリスト変数は 3 つだけです。
* デフォルトでは、prop は設定されたヒットの後は保持されません。eVar にはカスタムの有効期限があり、eVar がその後のイベントのクレジットを受け取らなくなった時期を判断できます。ただし、レポートの時間処理 [を使用する場合](../../../components/vrs/vrs-report-time-processing.md)、propとeVarの両方でカスタムアトリビューションモデルを使用できます。
