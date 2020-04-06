---
title: prop
description: 実装で使用できるカスタム変数。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# prop

Prop は、好きなだけ使用できるカスタム変数です。

>[!TIP] ほとんどの場合、eVar の使用をお勧めします。以前のバージョンの Adobe Analytics では、prop と eVar は互いに比べた利点と欠点がありました。ただし、アドビでは eVar を改善し、prop のほとんどすべての使用例を満たすようにしました。これらの 2 つのカスタム変数型の機能の比較については、[eVars](evar.md) を参照してください。

組織で prop を使用する場合は、その使用とロジックを必ず[ソリューションデザインドキュメント](../../prepare/solution-design.md)に記録してください。

## Adobe Experience Platform Launch の prop

Prop は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Props] section.

prop を選択して、値またはデータ要素を設定できます。別の Analytics 変数から値をコピーすることもできます。

## AppMeasurement および Launch カスタムコードエディターの s.prop1～s.prop75

各 prop 変数は、組織固有のカスタム値を含む文字列です。最大長は 100 バイトです。100 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.prop1 = "Example custom value";
```

## リスト prop

リスト prop は、変数が同じヒット内の複数の値を保持できるようにする prop に適用される設定です。この設定が有効でない場合、または誤った区切り文字が使用された場合、変数は単一の値として扱われます。

### リスト prop の設定

レポートスイート設定でリスト prop を有効にします。詳しくは、『管理者ユーザーガイド』の[トラフィック変数](/help/admin/admin/c-traffic-variables/traffic-var.md)を参照してください。目的の区切り文字が正しく設定されていることを確認します。デフォルトの区切り文字は提供されません。

>[!TIP] 実装で使用される一般的な区切り文字は、コンマ（`,`）、コロン（`:`）、セミコロン（`;`）、パイプ（`|`）です。実装に最適な任意の区切り文字を使用できます。

### リスト prop の設定

目的の区切り文字を使用してレポートスイートの設定でリスト prop を設定した後は、区切り文字を使用する以外に実装上の違いはありません。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT] リスト prop は、100 バイトの最大長に依存します。リスト prop は複数の値を含む可能性があるので、この制限に達しやすく切り捨てられます。この 100 バイトの制限に達した場合は、省略形や短縮値の使用を検討してください。

リストpropで同じ値を複数回設定した場合、重複は排除されます。レポート 分析ワークスペースは、値が表示されたヒット数をカウントし、値がデータに存在した回数はカウントしません。
