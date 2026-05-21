---
title: prop
description: 実装で使用できるカスタム変数。
feature: Appmeasurement Implementation
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
TQID: https://experienceleague.adobe.com/m1zwGOg7Fw26KdnqjqrOSekG8AehjIVsLKWMeaJfPY0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 623
ht-degree: 87%

---

# prop

*このヘルプページでは、prop の実装方法について説明します。 prop がディメンションとして機能する方法について詳しくは、『コンポーネントユーザガイド』の [prop](/help/components/dimensions/prop.md) を参照してください。*

prop は、好きなだけ使用できるカスタム変数です。 prop は、設定されたヒットの後は保持されません。

>[!TIP]
>
>ほとんどの場合、[eVar](evar.md) の使用をお勧めします。 以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。 しかし、AdobeはeVarを大幅に改善し、propのほぼすべてのユースケースに対応できるようになりました。

[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)がある場合、これらのカスタムディメンションを組織に固有の値に割り当てることができます。 使用可能な prop の数は、アドビとの契約によって異なります。 アドビとの契約でサポートされている場合は、最大 75 個の prop を使用できます。

## Web SDK を使用した prop

Propは次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` - リスト propが[個のフィールドのセット &#x200B;](#list-props-web-sdk)で指定されています。
* [&#x200B; データオブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75`、または`data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` - リスト propはこれらのフィールドに含まれています。

## Adobe Analytics 拡張機能を使用した prop

Prop は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL Props] セクションを見つけます。

Prop 値またはデータ要素に設定できます。 別の Analytics 変数から値をコピーすることもできます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.prop1 ～ s.prop75

各 prop 変数は、組織固有のカスタム値を含む文字列です。 最大長は 100 バイトです。100 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.prop1 = "Example custom value";
```

## リスト prop

リスト prop は、変数が同じヒット内の複数の値を保持できるようにする prop に適用される設定です。 この設定が有効でない場合、または誤った区切り文字が使用された場合、変数は単一の値として扱われます。

### リスト prop の設定

レポートスイート設定の[トラフィック変数](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)でリスト prop を有効にします。 目的の区切り文字が正しく設定されていることを確認します。 デフォルトの区切り文字は提供されません。

>[!TIP]
>
>実装で使用される一般的な区切り文字は、コンマ（`,`）、コロン（`:`）、セミコロン（`;`）、パイプ（`|`）です。 実装に最適な任意の非拡張 ASCII 区切り文字を使用できます。

### Web SDK を使用したリスト prop の設定 {#list-props-web-sdk}

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;を使用する場合、リスト propは`xdm._experience.analytics.customDimensions.listProps.prop1.values[]` ～ `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`にマッピングされます。 Web SDK は、レポートスイート設定にリストされた正しい区切り文字を自動的に使用します。 XDM フィールドで区切り文字を設定すると（例えば、`xdm._experience.analytics.customDimensions.props.prop1.delimiter`）、レポートスイート設定から自動的に取得された区切り文字が上書きされ、リスト prop 文字列の間違った解析につながる可能性があります。

[**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)&#x200B;を使用する場合、リスト propは標準propと同じフィールドを使用し、AppMeasurementの構文に従います。

### Adobe Analytics 拡張機能および AppMeasurement を使用したリスト prop の設定

目的の区切り文字を使用してレポートスイートの設定でリスト prop を設定した後は、区切り文字を使用する以外に実装上の違いはありません。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>リスト prop は、100 バイトの最大長に依存します。 リスト prop は複数の値を含む可能性があるので、この制限に達しやすく切り捨てられます。 この 100 バイトの制限に達した場合は、省略形や短縮値の使用を検討してください。

リスト prop で同じ値を複数回設定した場合、レポートでは重複が排除されます。 Analysis Workspace は、値が表示されたヒットの数をカウントし、値がデータに存在する回数はカウントしません。
