---
title: prop
description: 実装で使用できるカスタム変数。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 80%

---


# prop

*このヘルプページでは、propの実装方法を説明します。 For information on how props work as a dimension, see[prop](/help/components/dimensions/prop.md)in the Components user guide.*

Prop は、好きなだけ使用できるカスタム変数です。設定されたヒットを超えては持続しません。

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. 以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。

ソリューションデザイン [ドキュメントがある場合](/help/implement/prepare/solution-design.md)、これらのカスタムディメンションを組織に固有の値に割り当てることができます。 使用可能なpropの数は、アドビとの契約によって異なります。 アドビとの契約でサポートされている場合は、最大75個のpropを使用できます。

## Adobe Experience Platform Launch の prop

Prop は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL Props] セクションを見つけます。

propは値またはデータ要素に設定できます。 別の Analytics 変数から値をコピーすることもできます。

## AppMeasurement および Launch カスタムコードエディターの s.prop1～s.prop75

各 prop 変数は、組織固有のカスタム値を含む文字列です。最大長は 100 バイトです。100 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.prop1 = "Example custom value";
```

## リスト prop

リスト prop は、変数が同じヒット内の複数の値を保持できるようにする prop に適用される設定です。この設定が有効でない場合、または誤った区切り文字が使用された場合、変数は単一の値として扱われます。

### リスト prop の設定

レポートスイート設定でリスト prop を有効にします。詳しくは、『管理者ユーザーガイド』の[トラフィック変数](/help/admin/admin/c-traffic-variables/traffic-var.md)を参照してください。目的の区切り文字が正しく設定されていることを確認します。デフォルトの区切り文字は提供されません。

>[!TIP]
>
> 実装で使用される一般的な区切り文字は、コンマ（`,`）、コロン（`:`）、セミコロン（`;`）、パイプ（`|`）です。実装に最適な任意の区切り文字を使用できます。

### リスト prop の設定

目的の区切り文字を使用してレポートスイートの設定でリスト prop を設定した後は、区切り文字を使用する以外に実装上の違いはありません。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
> リスト prop は、100 バイトの最大長に依存します。リスト prop は複数の値を含む可能性があるので、この制限に達しやすく切り捨てられます。この 100 バイトの制限に達した場合は、省略形や短縮値の使用を検討してください。

リスト prop で同じ値を複数回設定した場合、レポートでは重複が排除されます。Analysis Workspace は、値が表示されたヒットの数をカウントし、値がデータに存在する回数はカウントしません。
