---
title: list
description: 同じヒットに複数の値を格納するカスタム変数。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# list

リスト変数は、好きなだけ使用できるカスタム変数です。 eVarと同様に機能しますが、同じヒットに複数の値を含めることができます。 リスト変数には文字制限はありません。

各リスト変数とそのロジックの使用方法を、ソリューションデザインドキュメントに記 [録してください](../../prepare/solution-design.md)。

> [!NOTE] リスト変数には、訪問者ごとの最新の250個の値が格納されます。 特定の訪問者に対して250を超えるユニーク値が存在する場合、最も古い値は指標に関連付けられません。

## レポートスイート設定でのリスト変数の設定

実装で各リスト変数を使用する前に、レポートスイートの設定で各リスト変数を設定してください。 See [Conversion variables](/help/admin/admin/conversion-var-admin/list-var-admin.md) in the Admin guide.

## Adobe Experience Platform Launchのリスト変数

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.list1 ～ s.list3、およびカスタムコードエディターの起動

各リスト変数は、組織固有のカスタム値を含む文字列です。 最大バイト数はありません。ただし、各値の最大値は255バイトです。 使用する区切り文字は、レポートスイート設定で変数を設定する際に決定されます。 複数の項目を区切る場合は、スペースを使用しないでください。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

> [!TIP] 同じヒットに重複する値を設定した場合、Adobeはそれらの値のすべてのインスタンスの重複を排除します。 例えば、を設定した場合、1つ `s.list1 = "Example,Example";`のインスタンスがレポートでカウントされます。

## リストpropと変数のリストを比較

リストpropとリスト変数の両方に、同じヒット内の複数の値を含めることができます。 ただし、これらの2つの変数型にはいくつかの主な違いがあります。

* どのpropもリストpropにすることができます。 すべてのpropがリストpropの場合、最大75個のリストpropを有効に設定できます。 使用できるリスト変数は3つだけです。
* リストpropには、変数全体に対して100バイトの制限があります。 リスト変数には、値ごとに255バイトの制限があり、合計バイト数の制限はありません。
* リストpropは、設定されたヒットの後は保持されません。 リスト変数には、必要な有効期限設定があります。 ただし、レポート [時間処理では](/help/components/vrs/vrs-report-time-processing.md)、リストpropとリスト変数の両方にカスタムアトリビューションを適用できます。
