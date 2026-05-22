---
description: 検索できるようにしたい各IDには、名前空間が割り当てられます。名前空間は、すべてのレポートスイートで使用されている任意の変数内のIDを識別するカスタム文字列です。
title: 名前空間
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
TQID: 'https://experienceleague.adobe.com/f9Pqs889VWpF4jyxX2GDBVdLyrDqWpHAkcHmDUizoGQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 942
ht-degree: 65%

---

# 名前空間

検索できるようにしたい各IDには、名前空間が割り当てられます。名前空間は、すべてのレポートスイートで使用されている任意の変数内のIDを識別するカスタム文字列です。

名前空間の文字列は、データプライバシー要求の一部として ID を提供する際に検索対象にしたいフィールドを識別するために使用されます。 データプライバシーリクエストが送信されると、そのリクエストには、リクエストで使用するデータ主体の ID を指定する JSON セクションが含まれます。 あるデータ主体に対する 1 回のリクエストの一部として、複数の ID を含めることができます。 JSONには以下が含まれます。

* 名前空間文字列を含む「名前空間」フィールド。
* ほとんどのAdobe Analytics リクエストの「type」フィールドには、「analytics」の値が含まれています。
* Analyticsが各レポートスイートの関連する名前空間変数で検索するIDを含む「値」フィールド。

詳しくは、[CX Enterprise Data Privacy API ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=ja)および標準ID名前空間の[&#x200B; リスト &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/api/appendix#standard-namespaces)を参照してください。 サンプルリクエストについて詳しくは、[アクセス／削除ジョブの作成](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/api/privacy-jobs#access-delete)を参照してください。

## Cookie ID

従来の Analytics トラッキング Cookie（Adobe Analytics ID（AAID）とも呼ばれる）：

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

値は、ダッシュで区切られた2つの16進数として指定する必要があります。 アルファベット文字である16進数はすべて、大文字を使用して指定する必要があります。 16進数の値には、先頭のゼロを指定しないでください（先頭のゼロが必要な場合は、非推奨のフォームで指定した値と同じ値との違いに注意してください）。

また、`"namespace": "AAID"` の代わりに（または追加として）`"namespaceId": 10` を使用することもできます。その場合、その形式を使用できるその他のアドビ製品が表示されます。

## 従来の Analytics トラッキング Cookie：廃止された形式

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

値は、2つの16桁の16進数または2つの19桁の10進数として指定する必要があります。 数字は、ダッシュ、アンダースコア、コロンで区切る必要があります。 いずれかの数値が十分な桁数を持たない場合、先頭にゼロを追加する必要があります。

## ID サービスの Cookie

```json
{
   "namespace": "ECID",
   "type": "standard",
   "value": "00497781304058976192356650736267671594"
}
```

値は、38 桁の 10 進数で指定される必要があります。 この数値をデータフィードまたは Data Warehouse レポートからの 2 つの mcvisid\_high/low 列または post\_msvisid\_high/low 列からプルしている場合、2 つの数値がそれぞれ 19 桁になるようにゼロを追加して、大きい値を先にして連結する必要があります。

また、`"namespace": "ECID"` の代わりに（または追加として）`"namespaceId": 4` を使用することもできます。その場合、その形式を使用できるその他のアドビ製品が表示されます。

>[!NOTE]
>
>Experience Cloud ID（ECID）の旧称は Marketing Cloud ID（MCID）ですが、既存のドキュメント内では、まだその名前で呼ばれている場合があります。
>
>これらの ID は、「analytics」以外の「type」値を使用する Analytics によってサポートされる唯一の ID です。

これらの Cookie ID の任意の値の部分の形式が、その ID について説明した形式に従っていない場合、「値が正しくフォーマットされていません」というエラーと共に、データプライバシー要求は失敗します。

新しい[プライバシー JavaScript](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) を使用して、これらの Cookie ID を収集するのが最も一般的です。これにより、これらの JSON ID の関連するすべてのキーと値のペアが自動的に提供されます。

この JavaScript コードによって、前述のフィールド（名前空間、タイプ、値）以外のキーと値のペアが JSON に入力されますが、Analytics でのデータプライバシーの処理で最も重要なのは、前述のフィールドです。他の方法で ID を収集している場合に提供する必要があるのも前述のフィールドのみです。

## カスタム訪問者 ID

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

名前空間も、カスタム訪問者ID用に事前定義されています。

## カスタム変数の ID

```json
{
"namespace":"Email Address",
"type": "analytics", 
"value": "john@xyz.com" 
}, 
{
    "namespace": "CRM ID", 
    "type": "analytics",
    "value": "123456-ABCD" 
}
```

カスタムのトラフィック変数またはコンバージョン変数（prop または eVar）の ID の場合は、変数に ID-DEVICE または ID-PERSON ラベルを設定してから、独自の名前空間の名前をその ID タイプに割り当てます。 [変数を ID-DEVICE または ID-PERSON としてラベル設定する際の名前空間の提供](/help/admin/tools/privacy-labeling/labels.md)を参照してください。

また、他の変数またはレポートスイートに対して以前に定義した名前空間を表示して、そのいずれかを再利用できるので、同じ名前空間を、そのタイプのIDを保存するすべてのレポートスイートに簡単に使用できます。 レポートスイート内の複数の変数に同じ名前空間を割り当てることもできます。 例えば、一部の顧客は、トラフィック変数とコンバージョン変数にCRM IDを保存し（ページによっては、どちらか一方または両方に格納されることがあります）、両方の変数に名前空間「CRM ID」を割り当てることができます。

>[!TIP]
>
>これが ID-DEVICE または ID-PERSON ラベルをこの変数に適用する際に指定した名前空間でもある場合を除いて、データプライバシー API に名前空間を指定する際に、変数のわかりやすい名前（レポート UI に表示される名前）や変数の番号（eVar12 など）を使用することはできません。 わかりやすい名前ではなく名前空間を使用することによって、同じユーザー ID ブロックで、複数のレポートスイートに対して正しい変数を指定できます。 例えば、ID が一部のレポートスイートで異なる eVar に含まれている場合や、フレンドリ名が一致しない場合（特定のレポートスイートに対してフレンドリ名がローカライズされている場合など）。

>[!CAUTION]
>
>名前空間 `visitorId` と `customVisitorId` は、Analytics のレガシートラッキング cookie と Analytics の顧客訪問者 ID を識別するために予約されています。 これらの名前空間を、カスタムトラフィックやコンバージョン変数に使用しないでください。

詳しくは、[変数を ID-DEVICE または ID-PERSON としてラベル設定する際の名前空間の提供](/help/admin/tools/privacy-labeling/labels.md)を参照してください。
