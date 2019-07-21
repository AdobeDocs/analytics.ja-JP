---
description: 検索可能にする各 ID には、名前空間が割り当てられます。名前空間とは、すべてのレポートスイートにわたって使用される任意の変数でその ID を識別するカスタム文字列のことです。
seo-description: 検索可能にする各 ID には、名前空間が割り当てられます。名前空間とは、すべてのレポートスイートにわたって使用される任意の変数でその ID を識別するカスタム文字列のことです。
seo-title: 名前空間
title: 名前空間
uuid: cab61844-3209-4980- b14c-6859de777606
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 名前空間

検索可能にする各 ID には、名前空間が割り当てられます。名前空間とは、すべてのレポートスイートにわたって使用される任意の変数でその ID を識別するカスタム文字列のことです。

名前空間の文字列は、GDPR 要求の一部として ID を提供する際に検索対象にしたいフィールドを識別するために使用されます。GDPR 要求が送信されると、その要求には、要求で使用するデータ主体の ID を指定する JSON セクションが含まれます。1 人のデータ主体の単一の要求の一部として、複数の ID を含めることができます。JSON の主な構成要素は以下のとおりです。

* 名前空間の文字列を含む「namespace」フィールド。
* 「type」フィールド。Adobe Analytics のほとんどの要求で、値は「analytics」になります。
* 「value」フィールド。値は、各レポートスイートの関連付けられた名前空間の変数に含まれている、Analytics による検索対象となる ID です。

詳しくは、[Experience Cloud GDPR API のドキュメント](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)を参照してください。

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

It is also acceptable to use `“namespaceId”: 10` instead of or in addition to `“namespace”: “AAID”` and you may see some other Adobe products use that form.

## 従来の Analytics トラッキング Cookie：廃止された形式

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

廃止された形式：

値は、16 桁の 2 つの 16 進数または 19 桁の 2 つの 10 進数で指定される必要があります。この値は、ダッシュ、アンダースコアまたはコロンで区切られる必要があります。いずれかの数値が十分な桁数を持たない場合、先頭にゼロを追加する必要があります。

## IDサービスcookie

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

値は、38 桁の 10 進数で指定される必要があります。この数値を、データフィードまたはデータウェアハウスレポートからの2つのmcvisid\_ high/lowまたはpost\_ msvisid\_ high列から取得する場合は、それぞれの2つの数値を19桁に固定し、それらの値を最初の値と連結する必要があります。

It is also acceptable to use: `“namespaceId”: 4` instead of or in addition to `“namespace”: “ECID”` and you may see some other Adobe products use that form.

>[!NOTE]
>
>Experience Cloud ID（ECID）は、以前はMarketing Cloud ID（MCID）と呼ばれていましたが、既存のドキュメントでもこの名前で参照されています。
>
>これらのIDは、"analytics"以外の「タイプ」値を使用するAnalyticsでサポートされている唯一のIDです。

これらの Cookie ID の任意の値の部分の形式が、その ID について説明した形式に従っていない場合、「値が正しくフォーマットされていません」というエラーと共に、GDPR 要求は失敗します。

新しい[プライバシー JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) を使用して、これらの Cookie ID を収集するのが最も一般的です。これにより、これらの JSON ID の関連するすべてのキーと値のペアが自動的に提供されます。

この JavaScript コードによって、前述のフィールド（名前空間、タイプ、値）以外のキーと値のペアが JSON に入力されますが、Analytics での GDPR の処理で最も重要なのは、前述のフィールドです。他の方法で ID を収集している場合に提供する必要があるのも前述のフィールドのみです。

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

カスタムのトラフィック変数またはコンバージョン変数（prop または eVar）の ID の場合は、変数に ID-DEVICE または ID-PERSON ラベルを設定してから、独自の名前空間の名前をその ID タイプに割り当てる必要があります。[変数を ID-DEVICE または ID-PERSON としてラベル設定する際の名前空間の提供](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)を参照してください。

以前に他の変数やレポートスイート用に定義した名前空間を確認し、再利用することもできます。そのため、このタイプの ID を格納するすべてのレポートスイートで、簡単に同一の名前空間を使用することができます。同一の名前空間をレポートスイート内の複数の変数に割り当てることもできます。例えば、CRM ID をトラフィック変数やコンバージョン変数（ページによっていずれか一方または両方）に格納しているお客様もいます。その場合は「CRM ID」という名前空間を両方の変数に割り当てることができます。

>[!NOTE]
>
>この変数にID- DEVICEまたはID- PERHERラベルを適用するときに指定した名前空間を除き、変数のわかりやすい名前（レポートUIに表示される名前）または変数の番号（eVar12など）を使用することはできません。わかりやすい名前ではなく名前空間を使用することによって、以下の場合に、同じユーザー ID ブロックで、複数のレポートスイートに対して正しい変数を指定できます。

* ID が一部のレポートスイートで異なる eVar である、または
* わかりやすい名前が一致しない（わかりやすい名前が特定のレポートスイート用にローカライズされている場合など）

詳しくは、[変数を ID-DEVICE または ID-PERSON としてラベル設定する際の名前空間の提供](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)を参照してください。
