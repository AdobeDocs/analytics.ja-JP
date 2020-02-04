---
title: prop
description: 実装で使用できるカスタム変数。
translation-type: tm+mt
source-git-commit: ddab63a4fe3b8f1a3187893eba1ac3a1eda3bc41

---


# prop

propは、好きなだけ使用できるカスタム変数です。

> [!TIP] ほとんどの場合、eVarの使用をお勧めします。 以前のバージョンのAdobe Analyticsでは、propとeVarは互いに利点と欠点がありました。 ただし、アドビではeVarを改善し、propのほとんどすべての使用例を満たすようにしました。 これらの [](evar.md) 2つのカスタム変数型の機能の比較については、eVarsを参照してください。

組織でpropを使用する場合は、その使用とロジックを必ずソリューションデザインドキュメントに記 [録してください](../../prepare/solution-design.md)。

## Adobe Experience Platform Launchのprop

propは、Analytics拡張の設定時（グローバル変数）またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「 [!UICONTROL Props] 」セクション

propを選択して、値またはデータ要素を設定できます。 別のAnalytics変数から値をコピーすることもできます。

## AppMeasurementのs.prop1 ～ s.prop75、およびカスタムコードエディターの起動

各prop変数は、組織固有のカスタム値を含む文字列です。 最大長は100バイトです。100バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
s.prop1 = "Example custom value";
```

## リストprop

リストpropは、変数が同じヒット内の複数の値を保持できるようにするpropに適用される設定です。 この設定が有効でない場合、または誤った区切り文字が使用された場合、変数は単一の値として扱われます。

### リストpropの設定

レポートスイート設定でリストpropを有効にします。 See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. 目的の区切り文字が正しく設定されていることを確認します。 デフォルトの区切り文字は提供されません。

> [!TIP] 実装で使用される一般的な区切り文字は、`,`コンマ()、コ`:`ロン()、セミコ`;`ロン()、パイプ(`|`)です。 実装に最適な任意の区切り文字を使用できます。

### リストpropの設定

目的の区切り文字を使用してレポートスイートの設定でリストpropを設定した後は、区切り文字を使用する以外に実装上の違いはありません。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] リストpropは、100バイトの最大長に依存します。 リストpropは複数の値を含む可能性があるので、この制限に達しやすく切り捨てられます。 この100バイトの制限に達した場合は、省略形や短縮値の使用を検討してください。
