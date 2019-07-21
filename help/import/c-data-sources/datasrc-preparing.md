---
description: データソース使用の準備に利用できる手順です。
seo-description: データソース使用の準備に利用できる手順です。
seo-title: データソースの使用の準備
solution: Analytics
subtopic: データソース
title: データソースの使用の準備
topic: 開発者と導入
uuid: 876ea069-574b-4e23-93b7- e3828bfd90f5
translation-type: tm+mt
source-git-commit: 887f48d2ea5f21b7db95a1a8f716f7da9cf43662

---


# データソースを使用するための準備

データソース使用の準備に利用できる手順です。

* [指標の指定と名前付け](../../import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [データディメンションの指定](../../import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [キャンペーントラッキングコード](../../import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [トランザクション ID](../../import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [データソースのデータで有効な日付範囲の指定](../../import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## 指標の指定と名前付け {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

It is important to understand the metrics or measurements that are contained in your data sources, such as *`Off-line Sales Revenue by Product`*, *`Returns by Product`*, or *`Ad Impressions by Campaign`*. これらは、レポート指標（イベント、prop、eVar）と関連付けることができる名前です。

データソースのデータに対して指標とイベントとの適切なマッピングを決定した後は、イベント名を、関連するデータソース指標に対応するわかりやすい名前に変更します。

管理ツールのヘルプの「[成功イベント](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=success_event)」を参照してください。

>[!NOTE]
>
>データソースのデータには、新しい空のイベントを使用することを強くお勧めしますが、事前に存在するイベントを使用する場合には意味がありません。

## データディメンションの指定 {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

データソースからインポートした指標の分類に使用するデータ（レポート）を指定して収集します。このデータを&#x200B;*`data dimensions`*（名前をつけて保存）する必要があります。

例えば、データソース指標で広告インプレッションを測定する場合は、キャンペーントラッキングコードをデータディメンションとすることが考えられます。オフラインの売上高を測定する場合、製品コード（SKU）をデータディメンションとして使用できます。

指標に複数のデータディメンションを定義できますが、各指標が、関連付けられた各データディメンションに対して、関連する値または値の組み合わせを提供する必要があります。例えば、オフラインの売上高指標をインポートし、これを&#x200B;*`Product`* および *`Partner`* データディメンションの場合、オフラインの売上高指標は製品とパートナーの各組み合わせ（例えば、合計売上高）に関連している必要があります。

>[!NOTE]
>
>どのデータディメンションでも分類できないトータル指標をインポートできます。

データソースで使用するデータディメンションを定義した後は、変数へのマッピングによってディメンションデータをマーケティングレポート内に組み込みます。標準のレポート（製品、トラッキングコード、検索キーワードなど）またはコンバージョントラフィック変数（eVar）のどちらかを使用します。

eVar を使用する場合は、既存の eVar と新規の eVar のどちらでもデータディメンションとして使用できます。データソースからデータディメンションを受け取る eVar を選択したら、必ずこれらの eVar に適切な名前を付けてください。

Analytics のヘルプの「[成功イベント](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=success_event)」を参照してください。

## キャンペーントラッキングコード {#section_468222796FF449ABAA90D88EB3264CB1}

成功イベントをインポートするだけでなく、関連する eVar 値をインポートすることもできます。例えば、キャンペーントラッキングコードを使用してオンラインアクティビティを追跡し、オフラインの指標に対してもキャンペーントラッキングコードを使用している場合、これらの指標をキャンペーントラッキングコードと共にインポートできます。これにより、オンラインとオフラインの両方の指標をキャンペーンレポートで表示できます。

データソース指標を関連する eVar 値と共にインポートしないと、eVar によって分類されたデータソース指標を表示できません。その場合は、トータル指標のみを表示できます。

## トランザクション ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

トランザクション ID は、オンラインのイベントとオフラインのイベントとを結びつけるのに使用します。

## データソースのデータで有効な日付範囲の指定 {#section_03AAB1291BDC4403BDC50905A78FDB71}

データソース指標（カスタムイベント）とデータディメンション（eVar）を定義したら、インポートするデータソースのデータの日付範囲を確認します。既存のレポートデータの範囲外になるデータソースをインポートすることはできません。

例えば、オンラインデータ追跡を実装する前のデータソースのデータをインポートすることはできません。データソースのデータは日別に分類する必要があります。
