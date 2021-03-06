---
title: eVar変数
description: 実装で使用できるカスタム変数。
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 86%

---

# eVar

*このヘルプページでは、eVar の実装方法について説明します。eVar がディメンションとして機能する方法について詳しくは、コンポーネントユーザーガイドの [eVar](/help/components/dimensions/evar.md) を参照してください。*

eVar は、好きなだけ使用できるカスタム変数です。[ソリューションデザインのドキュメント](/help/implement/prepare/solution-design.md)がある場合、組織固有のほとんどのディメンションは eVar になります。デフォルトでは、eVar は設定されたヒットを超えても保持されます。レポートスイート設定の「[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)」で、その有効期限と配分をカスタマイズできます。

使用可能な eVar の数は、アドビとの契約によって異なります。アドビとの契約でサポートされている場合は、最大 250 個の eVar を利用できます。

## レポートスイート設定での eVar の設定

実装で eVar を使用する前に、各 eVar をレポートスイートの設定で設定してください。詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。

## Web SDK を使用した eVar

eVar は [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) XDM フィールドの下 `_experience.analytics.customDimensions.eVars.eVar1` から `_experience.analytics.customDimensions.eVars.eVar250`.

## Adobe Analytics拡張機能を使用した eVar

eVar は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL eVars] セクションを見つけます。

eVar を値またはデータ要素に設定できます。別の Analytics 変数から値をコピーすることもできます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.eVar1～s.eVar250

各 eVar は、組織に固有のカスタム値を含む文字列です。最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.eVar1 = "Example custom value";
```

## カウンター eVar

eVar 値には通常、文字列値が含まれます。ただし、eVar にカウンターを代わりに含めるように設定できます。例えば、購入前におこなわれた内部検索の数をカウントするとします。テキスト値を設定する代わりに、次の構文を使用します。

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

eVar カウンターで小数点以下が 3 桁以上ある場合は、2 桁に四捨五入されます。eVar カウンターには負の値は設定できません。

>[!IMPORTANT]
>
>カウンター eVar を使用する前に、Admin Console で eVar を「カウンター」に設定する必要があります。詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。
