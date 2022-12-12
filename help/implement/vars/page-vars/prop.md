---
title: prop
description: 実装で使用できるカスタム変数。
feature: Variables
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
source-git-commit: 17b5185e5358d661157c20a2504cacdbd4a2cc3d
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 75%

---

# prop

*このヘルプページでは、prop の実装方法について説明します。prop がディメンションとして機能する方法について詳しくは、『コンポーネントユーザガイド』の [prop](/help/components/dimensions/prop.md) を参照してください。*

Prop は、好きなだけ使用できるカスタム変数です。prop は、設定されたヒットの後は保持されません。

>[!TIP]
>
>ほとんどの場合、[eVar](evar.md) の使用をお勧めします。以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)がある場合、これらのカスタムディメンションを組織に固有の値に割り当てることができます。使用可能な prop の数は、アドビとの契約によって異なります。アドビとの契約でサポートされている場合は、最大 75 個の prop を使用できます。

## Web SDK を使用した prop

prop は [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) XDM フィールドの下 `_experience.analytics.customDimensions.props.prop1` から `_experience.analytics.customDimensions.props.prop75`. リスト prop は、別々のフィールドセットで指定されます。

## Adobe Analytics拡張機能を使用する prop

Prop は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform データ収集](https://experience.adobe.com/data-collection)にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL Props] セクションを見つけます。

Prop 値またはデータ要素に設定できます。別の Analytics 変数から値をコピーすることもできます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.prop1～s.prop75

各 prop 変数は、組織固有のカスタム値を含む文字列です。最大長は 100 バイトです。100 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.prop1 = "Example custom value";
```

## リスト prop

リスト prop は、変数が同じヒット内の複数の値を保持できるようにする prop に適用される設定です。この設定が有効でない場合、または誤った区切り文字が使用された場合、変数は単一の値として扱われます。

### リスト prop の設定

でリスト prop を有効にする [トラフィック変数](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) 」をクリックします。 目的の区切り文字が正しく設定されていることを確認します。デフォルトの区切り文字は提供されません。

>[!TIP]
>
> 実装で使用される一般的な区切り文字は、コンマ（`,`）、コロン（`:`）、セミコロン（`;`）、パイプ（`|`）です。実装に最適な、拡張されていない ASCII 区切り文字を使用できます。

### Web SDK を使用したリスト prop の設定

目的の区切り文字を使用してレポートスイート設定でリスト prop を設定すると、リスト prop はAdobe Analyticsの `_experience.analytics.customDimensions.listProps.prop1.values[]` から `_experience.analytics.customDimensions.listProps.prop75.values[]`. Web SDK は、レポートスイートの設定に一覧表示されている正しい区切り文字を自動的に使用します。 XDM フィールドで区切り文字を設定した場合 ( 例： `_experience.analytics.customDimensions.props.prop1.delimiter`) を含めることをお勧めします。これは、レポートスイート設定から自動的に取得される区切り文字を上書きし、リスト prop 文字列を誤って解析する可能性があります。

### Adobe Analytics拡張機能と AppMeasurement を使用したリスト prop の設定

目的の区切り文字を使用してレポートスイートの設定でリスト prop を設定した後は、区切り文字を使用する以外に実装上の違いはありません。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
> リスト prop は、100 バイトの最大長に依存します。リスト prop は複数の値を含む可能性があるので、この制限に達しやすく切り捨てられます。この 100 バイトの制限に達した場合は、省略形や短縮値の使用を検討してください。

リスト prop で同じ値を複数回設定した場合、レポートでは重複が排除されます。Analysis Workspace は、値が表示されたヒットの数をカウントし、値がデータに存在する回数はカウントしません。
