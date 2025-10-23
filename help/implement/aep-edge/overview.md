---
title: Adobe Experience Platform Edge を使用した Adobe Analytics の実装
description: Adobe Analytics における Experience Platform の XDM データの使用の概要
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9845f1bc73b6cf5fd932c6896a50379ddd008c20
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 15%

---

# Adobe Experience Platform Edge Network を使用した Adobe Analytics の実装

Adobe Experience Platform Edge Network を使用すると、複数の製品宛てのデータを一元的な場所に送信できます。Edge Network は、適切な情報を目的の製品に転送します。この概念を使用すると、特に複数のデータソリューションにまたがる実装作業を統合できます。 Adobe Analyticsは、Edge Networkを使用してにデータを送信できる製品の 1 つです。

## Adobe Analytics が Edge Network データを処理する方法

Edge Network データとAppMeasurement データに送信されるデータの動作は異なるので、Edge Network ペイロードによってヒットの処理方法がAdobe Analyticsによって決まります。 詳しくは、[Adobe AnalyticsのEdge Network イベントタイプ ](hit-types.md) を参照してください。

Adobe Experience Platform Edge Networkに送信されるデータは、**XDM オブジェクト**、**データオブジェクト**、**コンテキストデータ** の 3 つの形式に従うことができます。 データストリームがAdobe Analyticsにデータを転送すると、Adobe Analyticsが処理できる形式に変換されます。

## `xdm` オブジェクト

[XDM](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home) （エクスペリエンスデータモデル）に基づいて作成したスキーマに準拠する。 XDM では、どのフィールドをイベントの一部として定義するかを柔軟に指定できます。Adobe Analyticsに特有の事前定義済みスキーマを使用する場合は、[Adobe Analytics ExperienceEvent スキーマフィールドグループ ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) をスキーマに追加できます。 追加したら、Web SDKの `xdm` オブジェクトを使用してこのスキーマにデータを入力し、レポートスイートにデータを送信できます。 データがEdge Networkに到達すると、XDM オブジェクトがAdobe Analyticsで認識できる形式に変換されます。

XDM フィールドの完全なリファレンスと、それらがAdobe Analytics変数にマッピングされる方法については、[Analytics への XDM オブジェクト変数のマッピング ](xdm-var-mapping.md) を参照してください。

>[!TIP]
>
>今後 [Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-landing) に移行する予定がある場合、Adobeでは、Adobe Analytics スキーマフィールドグループの使用を推奨しています。 代わりに、Adobeでは [ 独自のスキーマを作成 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) し、データストリームマッピングを使用して目的の Analytics 変数を設定することをお勧めします。 Customer Journey Analyticsへの移行を行う準備が整っても、この方法では prop と eVar のスキーマに固定されることはありません。

## `data` オブジェクト

`xdm` オブジェクトを使用する代わりに、`data` オブジェクトを使用することもできます。 このデータオブジェクトは、現在AppMeasurementを使用している実装に向けられているので、web SDKへのアップグレードがはるかに容易になります。 Edge Networkは、スキーマに準拠する必要なく、Adobe Analyticsに固有のフィールドの存在を検出します。

データオブジェクトフィールドの詳細およびAdobe Analytics変数へのマッピング方法については、[Analytics へのデータオブジェクト変数のマッピング ](data-var-mapping.md) を参照してください。

## コンテキストデータ変数

任意の形式でEdge Networkにデータを送信します。 `xdm` または `data` のオブジェクトフィールドに自動的にマッピングされないフィールドは、Adobe Analyticsに転送される際に [ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md) として含まれます。 次に、[ 処理ルール ](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) を使用して、目的のフィールドをそれぞれの Analytics 変数にマッピングする必要があります。

例えば、次のようなカスタム XDM スキーマがあるとします。

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

その後、これらのフィールドは、処理ルールインターフェイスで使用できるコンテキストデータキーになります。

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```

特定のコンテキストデータ変数ペイロード（キーと値を含む）の最大サイズは 32 KB です。 関連するフィールドを調整して、[`xdm`](xdm-var-mapping.md) オブジェクトまたは [`data`](data-var-mapping.md) オブジェクト内のAdobe Analyticsで認識されるようにすることで、このペイロードのサイズを小さくすることができます。
