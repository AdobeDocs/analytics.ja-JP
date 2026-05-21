---
title: list
description: 同じヒットに複数の値を格納するカスタム変数。
feature: Appmeasurement Implementation
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
TQID: https://experienceleague.adobe.com/LpUX55ZGYgm7Z2-P4uAwH-rV88JMbi2661i4f9RYd-Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 74%

---

# list

リスト変数は、好きなだけ使用できるカスタム変数です。 eVar と同様に機能しますが、同じヒットに複数の値を含めることができます。 リスト変数には文字制限はありません。

各リスト変数とそのロジックの使用方法を、[ソリューションデザインドキュメント](../../prepare/solution-design.md)に記録してください。

>[!NOTE]
>
>リスト変数は、[ レポートスイート設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)の[!UICONTROL 最大値]設定に基づいて、訪問者ごとに最新の値を保存します。 最大250個の値がサポートされています。 [!UICONTROL 最大値]設定で許可されている値よりも一意の値が多い場合、最も古い値は指標に関連付けられません。

## レポートスイート設定でのリスト変数の設定

実装で各リスト変数を使用する前に、レポートスイートの設定で各リスト変数を設定してください。 詳しくは、管理者ガイドの[コンバージョン変数](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)を参照してください。 この手順は、すべての実装方法に適用されます。

## Web SDK を使用したリスト変数

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;を使用する場合、リスト変数はXDM フィールド `xdm._experience.analytics.customDimensions.lists.list1.list[]`から`xdm._experience.analytics.customDimensions.lists.list3.list[]`を使用します。 各配列要素には、各文字列を含む `"value"` オブジェクトが含まれます。 区切り文字を指定する必要はありません。Adobe データ収集サーバーは、[ レポートスイート設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)で設定された正しい区切り文字を自動的に検出して含めます。

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
>Adobe XDM スキーマには、各 `list[]` 配列の `value` オブジェクトに加えて `key` オブジェクトが含まれています。 アドビは、データを Adobe Analytics に送信するときにこれらの `key` オブジェクトを使用しません。

[**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)&#x200B;を使用する場合、リスト変数はAppMeasurementの構文に従って`data.__adobe.analytics.list1` ～ `data.adobe.analytics.list3`を使用します。 [ レポートスイート設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)で正しい区切り文字を使用していることを確認してください。

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

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.list1～s.list3

各リスト変数は、組織固有のカスタム値を含む文字列です。 この変数には最大バイト数はありませんが、個々の値の最大制限は255 バイトです。 使用する区切り文字は、[レポートスイート設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)で変数を設定する際に決定されます。 複数の項目を区切る場合は、スペースを使用しないでください。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>同じヒットに重複する値を設定した場合、アドビはそれらの値のすべてのインスタンスの重複を排除します。 例えば、`s.list1 = "Brick,Brick";` を設定した場合、1 つのインスタンスがレポートでカウントされます。

## リスト prop と変数のリストを比較

リスト prop とリスト変数の両方に、同じヒット内の複数の値を含めることができます。 ただし、これらの 2 つの変数型にはいくつかの主な違いがあります。

* どの prop もリスト prop にすることができます。 すべての prop がリスト prop の場合、最大 75 個のリスト prop を有効に設定できます。 使用できるリスト変数は 3 つだけです。
* リスト prop には、変数全体に対して 100 バイトの制限があります。 リスト変数には、値ごとに 255 バイトの制限があり、合計バイト数の制限はありません。
* リスト prop は、設定されたヒットの後は保持されません。 リスト変数には、必要な有効期限設定があります。 ただし、[レポート時間処理](/help/components/vrs/vrs-report-time-processing.md)では、リスト prop とリスト変数の両方にカスタムアトリビューションを適用できます。
