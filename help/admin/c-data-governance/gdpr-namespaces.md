---
description: 検索可能にする各 ID には、名前空間が割り当てられます。名前空間とは、すべてのレポートスイートにわたって使用される任意の変数でその ID を識別するカスタム文字列のことです。
seo-description: 検索可能にする各 ID には、名前空間が割り当てられます。名前空間とは、すべてのレポートスイートにわたって使用される任意の変数でその ID を識別するカスタム文字列のことです。
seo-title: 名前空間
title: 名前空間
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# 名前空間

検索可能にする各 ID には、名前空間が割り当てられます。名前空間とは、すべてのレポートスイートにわたって使用される任意の変数でその ID を識別するカスタム文字列のことです。

名前空間文字列は、データプライバシーリクエストの一部としてIDを指定する際に検索するフィールドを識別するために使用されます。 データプライバシーリクエストが送信されると、リクエストに使用するデータの件名IDを指定するJSONセクションがリクエストに含まれます。 1 人のデータ主体の単一の要求の一部として、複数の ID を含めることができます。JSON の主な構成要素は以下のとおりです。

* 名前空間の文字列を含む「namespace」フィールド。
* 「type」フィールド。Adobe Analytics のほとんどの要求で、値は「analytics」になります。
* 「value」フィールド。値は、各レポートスイートの関連付けられた名前空間の変数に含まれている、Analytics による検索対象となる ID です。

Refer to the [Experience Cloud Data Privacy API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details.

<!-- Meike, I converted this table to headings and text to fix a validation error. -Bob -->

## Cookie ID

従来の Analytics トラッキング Cookie（Adobe Analytics ID（AAID）とも呼ばれる）：

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

値は、ダッシュで区切った 2 つの 16 進数で指定される必要があります。アルファベットのすべての 16 進数の桁は、大文字を使用して指定する必要があります。16 進数値は、先頭にゼロを持つことはできません（先頭にゼロが必要だった廃止された形式とは異なることに注意してください）。

また、`"namespace": "AAID"` の代わりに（または追加として）`"namespaceId": 10` を使用することもできます。その場合、その形式を使用できるその他のアドビ製品が表示されます。

## 従来の Analytics トラッキング Cookie：廃止された形式

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

廃止された形式：

値は、16 桁の 2 つの 16 進数または 19 桁の 2 つの 10 進数で指定される必要があります。この値は、ダッシュ、アンダースコアまたはコロンで区切られる必要があります。いずれかの数値に十分な桁数がない場合は、先頭にゼロを追加する必要があります。

## ID サービスの cookie

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

値は、38 桁の 10 進数で指定される必要があります。この数値をデータフィードまたは Data Warehouse レポートからの 2 つの mcvisid\_high/low 列または post\_msvisid\_high/low 列からプルしている場合、2 つの数値がそれぞれ 19 桁になるようにゼロを追加して、大きい値を先にして連結する必要があります。

また、`"namespace": "ECID"` の代わりに（または追加として）`"namespaceId": 4` を使用することもできます。その場合、その形式を使用できるその他のアドビ製品が表示されます。

>[!NOTE]
>
>Experience Cloud ID（ECID）の旧称は Marketing Cloud ID（MCID）ですが、既存のドキュメント内では、まだその名前で呼ばれている場合があります。
>
>これらの ID は、「analytics」以外の「type」値を使用する Analytics によってサポートされる唯一の ID です。

これらのcookie IDの値部分の形式が、そのIDに対して記述された形式に従っていない場合、データプライバシーリクエストは失敗し、「値が正しく形式設定されていません」というエラーが表示されます。

新しい[プライバシー JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) を使用して、これらの Cookie ID を収集するのが最も一般的です。これにより、これらの JSON ID の関連するすべてのキーと値のペアが自動的に提供されます。

このJavaScriptコードは、上記に示したキーと値のペア（名前空間、タイプ、値）以外に、他のキーと値のペアをJSONに入力しますが、上記のフィールドはAnalyticsデータプライバシー処理で最も重要で、他の方法でIDを収集する場合に指定する必要がある唯一のフィールドです。

## カスタム訪問者 ID

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

カスタム訪問者 ID の名前空間も事前定義されています。

## カスタム変数の ID

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

カスタムのトラフィック変数またはコンバージョン変数（prop または eVar）の ID の場合は、変数に ID-DEVICE または ID-PERSON ラベルを設定してから、独自の名前空間の名前をその ID タイプに割り当てます。See [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](gdpr-labels.md)

以前に他の変数やレポートスイート用に定義した名前空間を確認し、再利用することもできます。そのため、このタイプの ID を格納するすべてのレポートスイートで、簡単に同一の名前空間を使用することができます。同一の名前空間をレポートスイート内の複数の変数に割り当てることもできます。例えば、CRM ID をトラフィック変数やコンバージョン変数（ページによっていずれか一方または両方）に格納しているお客様もいます。その場合は「CRM ID」という名前空間を両方の変数に割り当てることができます。

> [!TIP] データプライバシーAPIに名前空間を指定する場合は、変数のわかりやすい名前（レポートUIに表示される名前）や変数の番号（eVar12など）を使用しないでください。ただし、ID-DEVICEまたはID-PERSONラベルを適用する際に指定した名前空間は例外です。 わかりやすい名前ではなく名前空間を使用することによって、同じユーザー ID ブロックで、複数のレポートスイートに対して正しい変数を指定できます。例えば、IDが一部のレポートスイートで異なるeVarに含まれている場合や、フレンドリ名が一致しない場合（特定のレポートスイートに対してフレンドリ名がローカライズされている場合など）。

> [!CAUTION] 名前空間「visitorId」と「customVisitorId」は、Analytics の従来のトラッキング cookie と Analytics の顧客訪問者 ID を識別するために予約されています。これらの名前空間を、カスタムトラフィックやコンバージョン変数に使用しないでください。

For more information, see [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](/help/admin/c-data-governance/gdpr-labels.md)
