---
title: list
description: 同じヒットに複数の値を格納するカスタム変数。
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: e8a6400895110a14306e2dc9465e5de03d1b5d73
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 62%

---

# リスト

リスト変数は、好きなだけ使用できるカスタム変数です。eVar と同様に機能しますが、同じヒットに複数の値を含めることができます。リスト変数には文字制限はありません。

各リスト変数とそのロジックの使用方法を、[ソリューションデザインドキュメント](../../prepare/solution-design.md)に記録してください。

>[!NOTE]
>
> リスト変数には、訪問者ごとの最新の 250 個の値が格納されます。特定の訪問者に対して 250 を超える一意の値が存在する場合、最も古い値は指標に関連付けられません。

## レポートスイート設定でのリスト変数の設定

実装で各リスト変数を使用する前に、レポートスイートの設定で各リスト変数を設定してください。詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/list-var-admin.md)を参照してください。この手順は、すべての実装方法に適用されます。

>[!NOTE]
>
>Web SDK でマッピングされたフィールドを使用して実装されたリスト変数は、コンマ (&#39;`,`&#39;) です。

## Web SDK を使用した変数のリスト

リスト変数は、 [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) XDM フィールドの下 `_experience.analytics.customDimensions.lists.list1.list[]` から `_experience.analytics.customDimensions.lists.list3.list[]`. 各配列要素には、 `"value"` 各文字列を格納するオブジェクト。 例えば、次の XDM オブジェクトは `list1` 変数 `"Example value 1,Example value 2,Example value 3"`.

```json
"xdm": {
    "_experience": {
        "analytics": {
            "customDimensions": {
                "lists": {
                    "list1": {
                        "list": [
                            {
                                "value": "Example value 1"
                            },
                            {
                                "value": "Example value 2"
                            },
                            {
                                "value": "Example value 3"
                            }
                        ]
                    }
                }
            }
        }
    }
}
```

組織で、コンマ (&#39;`,`&#39;) の代わりに、目的の区切り文字を含むリスト文字列全体をカスタム XDM フィールドに渡すことができます。 で目的の区切り文字を受け入れるように list 変数が設定されていることを確認します。 [レポートスイートの設定](/help/admin/admin/conversion-var-admin/list-var-admin.md).

```json
"xdm": {
    "custom_object": {
        "custom_path": {
            "custom_listvar": "Example value 1|Example value 2|Example value 3"
        }
    }
}
```

次のいずれかを実行できます。

* カスタム XDM フィールドを Adobe Experience Edge で目的のリスト変数にマッピングする。または
* 目的のリスト var をコンテキストデータ変数で上書きする処理ルールを作成します。 詳しくは、 [他の XDM フィールドの Analytics 変数へのマッピング](../../aep-edge/variable-mapping.md#mapping-other-xdm-fields-to-analytics-variables).

## Adobe Analytics拡張機能を使用したリスト変数

Adobe Analytics拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.list1～s.list3

各リスト変数は、組織固有のカスタム値を含む文字列です。最大バイト数はありません。ただし、各値の最大値は 255 バイトです。使用する区切り文字は、 [レポートスイートの設定](/help/admin/admin/conversion-var-admin/list-var-admin.md). 複数の項目を区切る場合は、スペースを使用しないでください。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
> 同じヒットに重複する値を設定した場合、アドビはそれらの値のすべてのインスタンスの重複を排除します。例えば、`s.list1 = "Brick,Brick";` を設定した場合、1 つのインスタンスがレポートでカウントされます。

## リスト prop と変数のリストを比較

リスト prop とリスト変数の両方に、同じヒット内の複数の値を含めることができます。ただし、これらの 2 つの変数型にはいくつかの主な違いがあります。

* どの prop もリスト prop にすることができます。すべての prop がリスト prop の場合、最大 75 個のリスト prop を有効に設定できます。使用できるリスト変数は 3 つだけです。
* リスト prop には、変数全体に対して 100 バイトの制限があります。リスト変数には、値ごとに 255 バイトの制限があり、合計バイト数の制限はありません。
* リスト prop は、設定されたヒットの後は保持されません。リスト変数には、必要な有効期限設定があります。ただし、[レポート時間処理](/help/components/vrs/vrs-report-time-processing.md)では、リスト prop とリスト変数の両方にカスタムアトリビューションを適用できます。
