---
title: state
description: （退職済み）は、「訪問者の状態レポート」に入力されました。このレポートは使用できなくなりました。
feature: Appmeasurement Implementation
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
TQID: https://experienceleague.adobe.com/3GhnJJj6gxEt0Qiefd4siS6-YzDbOw4hdY4IsNhwYDU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 87%

---

# state

>[!IMPORTANT]
>
>この変数は廃止されており、Analysis Workspace で使用できるディメンションではありません。 代わりに[US States](/help/components/dimensions/us-states.md) ディメンションを使用します。このディメンションは、AppMeasurementが訪問者の場所に基づいて自動的に収集します。

以前のバージョンの Adobe Analytics では、訪問者が小売サイトの発送先情報を入力したときに `state` 変数が使用されていました。 機能的には prop と同じですが、Analysis Workspace では使用できません。

## Adobe Analytics 拡張機能を使用した state

state は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL state] セクションを見つけます。

state は任意の文字列値またはデータ要素に設定できます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.state

`s.state` 変数は、通常、訪問者の州または郡を含む文字列です。 州名と 2 文字の州コードはどちらも有効です。 最大値は 50 バイトです。より長い値は切り捨てられます。 デフォルト値は空の文字列です。

```js
s.state = "Utah";
```
