---
title: list
description: 同じヒットに複数の値を格納するカスタム変数。
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 87%

---

# list

リスト変数は、好きなだけ使用できるカスタム変数です。eVar と同様に機能しますが、同じヒットに複数の値を含めることができます。リスト変数には文字制限はありません。

各リスト変数とそのロジックの使用方法を、[ソリューションデザインドキュメント](../../prepare/solution-design.md)に記録してください。

>[!NOTE]
>
> リスト変数には、訪問者ごとの最新の 250 個の値が格納されます。特定の訪問者に対して 250 を超える一意の値が存在する場合、最も古い値は指標に関連付けられません。

## レポートスイート設定でのリスト変数の設定

実装で各リスト変数を使用する前に、レポートスイートの設定で各リスト変数を設定してください。詳しくは、管理者ガイドの[コンバージョン変数](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)を参照してください。この手順は、すべての実装方法に適用されます。

## Web SDK を使用したリスト変数

を使用する場合、 [**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;の場合、リスト変数は XDM フィールドを使用します `xdm._experience.analytics.customDimensions.lists.list1.list[]` から `xdm._experience.analytics.customDimensions.lists.list3.list[]`. 各配列要素には、各文字列を含む `"value"` オブジェクトが含まれます。 区切り文字を指定する必要はありません。Adobeデータ収集サーバーは、 [レポートスイートの設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

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

>[!NOTE]
>
>Adobe XDM スキーマには、各 `list[]` 配列の `value` オブジェクトに加えて `key` オブジェクトが含まれています。アドビは、データを Adobe Analytics に送信するときにこれらの `key` オブジェクトを使用しません。

を使用する場合、 [**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)、リスト変数は `data.__adobe.analytics.list1` - `data.adobe.analytics.list3` 次のAppMeasurement構文に従います。 で設定されている正しい区切り文字を使用していることを確認してください。 [レポートスイートの設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

```json
"data": {
  "__adobe": {
    "analytics": {
      "list1": "Example value 1,Example value 2,Example value 3"
    }
  }
}
```

## Adobe Analytics 拡張機能を使用したリスト変数

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.list1～s.list3

各リスト変数は、組織固有のカスタム値を含む文字列です。最大バイト数はありません。ただし、各値の最大値は 255 バイトです。使用する区切り文字は、[レポートスイート設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)で変数を設定する際に決定されます。複数の項目を区切る場合は、スペースを使用しないでください。

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
