---
description: 検索可能な各IDに名前空間が割り当てられます。これは、すべてのレポートスイートで使用される任意の変数内のそのIDを識別するカスタム文字列です。
title: 名前空間
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 名前空間

検索可能な各IDに名前空間が割り当てられます。これは、すべてのレポートスイートで使用される任意の変数内のそのIDを識別するカスタム文字列です。

名前空間の文字列は、データプライバシー要求の一部として ID を提供する際に検索対象にしたいフィールドを識別するために使用されます。データプライバシー要求が送信されると、その要求には、要求で使用するデータ主体の ID を指定する JSON セクションが含まれます。1つのデータサブジェクトに対する1つのリクエストの一部として、複数のIDを含めることができます。 JSONには次のものが含まれます。

* 名前空間文字列を含む「名前空間」フィールド。
* ほとんどのAdobe Analyticsリクエストの「タイプ」フィールドには、「analytics」という値が含まれます。
* 各レポートスイートの関連する名前空間変数でAnalyticsが検索する必要のあるIDを含む「値」フィールド。

詳しくは、[Experience Cloud データプライバシー API のドキュメント](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/technical_overview/privacy_service_overview/privacy_service_overview.md)を参照してください。

## Cookie ID

従来の Analytics トラッキング Cookie（Adobe Analytics ID（AAID）とも呼ばれる）：

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

この値は、2つの16進数で区切ってダッシュで指定する必要があります。 英字の16進数字はすべて、大文字を使用して指定する必要があります。 16進数値の先頭に0を付けることはできません(廃止された形式で指定された値と同じ値の違いに注意してください（先頭の0が必要です）。

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

この値は、16桁の16進数を2つ、または19桁の10進数を2つとして指定する必要があります。 数字は、ダッシュ、アンダースコアまたはコロンで区切る必要があります。 いずれかの数値が十分な桁数を持たない場合、先頭にゼロを追加する必要があります。

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

>[!NOTE]Experience Cloud ID（ECID）の旧称は Marketing Cloud ID（MCID）ですが、既存のドキュメント内では、まだその名前で呼ばれている場合があります。
>
>これらの ID は、「analytics」以外の「type」値を使用する Analytics によってサポートされる唯一の ID です。

これらの Cookie ID の任意の値の部分の形式が、その ID について説明した形式に従っていない場合、「値が正しくフォーマットされていません」というエラーと共に、データプライバシー要求は失敗します。

新しい[プライバシー JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) を使用して、これらの Cookie ID を収集するのが最も一般的です。これにより、これらの JSON ID の関連するすべてのキーと値のペアが自動的に提供されます。

この JavaScript コードによって、前述のフィールド（名前空間、タイプ、値）以外のキーと値のペアが JSON に入力されますが、Analytics でのデータプライバシーの処理で最も重要なのは、前述のフィールドです。他の方法で ID を収集している場合に提供する必要があるのも前述のフィールドのみです。

## カスタム訪問者 ID

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

この名前空間は、カスタム訪問者IDに対しても事前に定義されます。

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

カスタムのトラフィック変数またはコンバージョン変数（prop または eVar）の ID の場合は、変数に ID-DEVICE または ID-PERSON ラベルを設定してから、独自の名前空間の名前をその ID タイプに割り当てます。[変数を ID-DEVICE または ID-PERSON としてラベル設定する際の名前空間の提供](gdpr-labels.md)を参照してください。

また、他の変数やレポートスイートに対して以前に定義した名前空間を表示し、そのうちの1つを再利用することで、同じ名前空間を、そのタイプのIDを保存するすべてのレポートスイートで簡単に使用できます。 また、同じ変数をレポートスイート内の複数の名前空間に割り当てることもできます。 例えば、一部の顧客は、CRM IDをトラフィック変数とコンバージョン変数（ページによっては、どちらか一方または両方に格納される場合があります）に格納し、両方の変数に名前空間「CRM ID」を割り当てることができます。

>[!TIP]これが ID-DEVICE または ID-PERSON ラベルをこの変数に適用する際に指定した名前空間でもある場合を除いて、データプライバシー API に名前空間を指定する際に、変数のわかりやすい名前（レポート UI に表示される名前）や変数の番号（eVar12 など）を使用することはできません。わかりやすい名前ではなく名前空間を使用することによって、同じユーザー ID ブロックで、複数のレポートスイートに対して正しい変数を指定できます。例えば、ID が一部のレポートスイートで異なる eVar に含まれている場合や、フレンドリ名が一致しない場合（特定のレポートスイートに対してフレンドリ名がローカライズされている場合など）。

>[!CAUTION] 名前空間「visitorId」と「customVisitorId」は、Analytics の従来のトラッキング cookie と Analytics の顧客訪問者 ID を識別するために予約されています。これらの名前空間を、カスタムトラフィックやコンバージョン変数に使用しないでください。

詳しくは、[変数を ID-DEVICE または ID-PERSON としてラベル設定する際の名前空間の提供](/help/admin/c-data-governance/gdpr-labels.md)を参照してください。
