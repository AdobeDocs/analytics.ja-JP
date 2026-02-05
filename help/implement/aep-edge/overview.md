---
title: Adobe Experience Platform Edge を使用した Adobe Analytics の実装
description: Adobe Analytics における Experience Platform の XDM データの使用の概要
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9845f1bc73b6cf5fd932c6896a50379ddd008c20
workflow-type: ht
source-wordcount: '550'
ht-degree: 100%

---

# Adobe Experience Platform Edge Network を使用した Adobe Analytics の実装

Adobe Experience Platform Edge Network を使用すると、複数の製品宛てのデータを一元的な場所に送信できます。Edge Network は、適切な情報を目的の製品に転送します。この概念を使用すると、特に複数のデータソリューションにまたがる実装作業を統合できます。Adobe Analytics は、Edge Network を使用してデータを送信できる製品の 1 つです。

## Adobe Analytics が Edge Network データを処理する方法

Edge Network に送信したデータと AppMeasurement データの動作は異なるので、Edge Network のペイロードによって Adobe Analytics がヒットを処理する方法が決まります。詳しくは、[Adobe Analytics の Edge Network イベントタイプ](hit-types.md)を参照してください。

Adobe Experience Platform Edge Network に送信されるデータは、**XDM オブジェクト**、**データオブジェクト**、**コンテキストデータ** の 3 つの形式に従うことができます。データストリームでデータを Adobe Analytics に転送すると、データは Adobe Analytics が処理できる形式に変換されます。

## `xdm` オブジェクト

[XDM](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home)（エクスペリエンスデータモデル）に基づいて作成したスキーマに準拠します。XDM では、どのフィールドをイベントの一部として定義するかを柔軟に指定できます。Adobe Analytics 固有の事前定義済みスキーマを使用する場合は、[Adobe Analytics ExperienceEvent スキーマフィールドグループ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)をスキーマに追加できます。追加したら、Web SDK の `xdm` オブジェクトを使用してこのスキーマにデータを入力し、レポートスイートにデータを送信できます。データが Edge Network に到達すると、XDM オブジェクトは Adobe Analytics が理解できる形式に変換されます。

XDM フィールドと、これらが Analytics 変数にマッピングされる方法の完全なリファレンスについて詳しくは、[Adobe Analytics への XDM オブジェクト変数のマッピング](xdm-var-mapping.md)を参照してください。

>[!TIP]
>
>今後 [Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-landing) に移行する予定がある場合、アドビでは、Adobe Analytics スキーマフィールドグループを使用しないことをお勧めします。代わりに、アドビでは、[独自のスキーマを作成し](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect)、データストリームマッピングを使用して目的の Analytics 変数を入力することをお勧めします。この戦略では、Customer Journey Analytics に移行する準備が整った際に、prop と eVar のスキーマにロックされることはありません。

## `data` オブジェクト

`xdm` オブジェクトを使用する代わりに、`data` オブジェクトを使用することもできます。このデータオブジェクトは、現在 AppMeasurement を使用している実装向けに設計され、Web SDK へのアップグレードがはるかに簡単になります。Edge Network は、スキーマに準拠する必要なく、Adobe Analytics 固有のフィールドの存在を検出します。

データオブジェクトフィールドと、これらが Analytics 変数にマッピングされる方法の完全なリファレンスについて詳しくは、[Adobe Analytics へのデータオブジェクト変数のマッピング](data-var-mapping.md)を参照してください。

## コンテキストデータ変数

任意の形式でデータを Edge Network に送信します。`xdm` または `data` オブジェクトフィールドに自動的にマッピングされないフィールドは、Adobe Analytics に転送される際に[コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)として含まれます。 次に、[処理ルール](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)を使用して、目的のフィールドをそれぞれの Analytics 変数にマッピングする必要があります。

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

特定のコンテキストデータ変数ペイロード（キーと値を含む）の最大サイズは 32 KB です。関連するフィールドを調整して、[`xdm`](xdm-var-mapping.md) または [`data`](data-var-mapping.md) オブジェクト内の Adobe Analytics で認識されるようにすることで、このペイロードのサイズを縮小できます。
