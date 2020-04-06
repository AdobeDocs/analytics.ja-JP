---
description: データソース使用の準備に利用できる手順です。
subtopic: Data sources
title: データソースを使用するための準備
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# データソースを使用するための準備

データソース使用の準備に利用できる手順です。

* [指標の識別と命名](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [データディメンションの指定](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [キャンペーントラッキングコード](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [トランザクション ID](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [データソースデータの有効な日付範囲の指定](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## 指標の識別と命名 {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

データソースに含まれる指標や測定（例：*`Off-line Sales Revenue by Product`*、*`Returns by Product`*、*`Ad Impressions by Campaign`*）について理解することが重要です。これらの名前は、レポート指標(イベント、prop、eVar)に関連付けることができます。

データソースデータに対する適切な指標とイベントのマッピングを決定したら、イベントの名前を、関連するデータソース指標に適したわかりやすい名前に変更します。

管理ツール [ヘルプの成功イベント](https://marketing.adobe.com/resources/help/ja_JP/reference/success_event.html) (Success Success Success Success Success Success Success Success Success Success Tools)を参照してください。

>[!NOTE]アドビではデータソースのデータに新しい空のイベントを使用することを強くお勧めしますが、既存のイベントの使用が適する場合も稀にあります。

## データディメンションの指定 {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

データソースからインポートされた指標の分類に使用するデータ（レポート）を特定し、収集します。 このデータは、*`data dimensions`* と呼ばれます。

例えば、データソース指標で広告インプレッション数を測定する場合、データディメンションはおそらくキャンペーントラッキングコードです。 オフラインの売上高を測定する場合は、製品コード(SKU)をデータディメンションとして使用できます。

指標に対して複数のデータディメンションを定義できますが、各指標は、関連する各データディメンションに対して関連する値または値の組み合わせを提供する必要があります。 例えば、オフラインの売上高指標を読み込み、これを&#x200B;*`Product`* および&#x200B;*`Partner`* の各データディメンションに関連付ける場合、オフラインの売上高指標は製品とパートナーの各組み合わせ（合計売上高など）に関連している必要があります。

>[!NOTE]どのデータディメンションでも分類できないトータル指標を読み込むこともできます。

データソースで使用するデータディメンションを定義した後、ディメンションデータを変数にマッピングしてマーケティングレポートに統合します。 標準レポート（製品、トラッキングコード、検索キーワードなど）またはコンバージョントラフィック変数(eVar)を使用します。

eVarを使用する場合、既存のeVarまたは新しいeVarのいずれかをデータディメンションとして使用できます。 データソースからデータディメンションを受け取るeVarを選択した後、必ず適切な名前を付けてください。

Analyticsヘルプの [成功イベント](https://marketing.adobe.com/resources/help/ja_JP/reference/success_event.html) （英語のみ）を参照してください。

## キャンペーントラッキングコード {#section_468222796FF449ABAA90D88EB3264CB1}

成功イベントのインポートに加え、関連するeVar値をインポートすることもできます。 例えば、キャンペーン追跡コードを使用してオンラインアクティビティを追跡し、オフライン指標のキャンペーン追跡コードがある場合、キャンペーン追跡コードを使用して指標をインポートできます。 この方法を使用すると、オンラインとオフラインの両方の指標を表示レポートでキャンペーンできます。

データソース指標を関連するeVar値と共にインポートしない場合、eVarで分類された表示データソース指標はインポートできません。 トータル指標のみが表示されます。

## トランザクション ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

トランザクションIDは、オンライントランザクションをオフラインイベントに接続するために使用されます。

## データソースデータの有効な日付範囲の指定 {#section_03AAB1291BDC4403BDC50905A78FDB71}

データソース指標(カスタムイベント)とデータディメンション(eVar)を定義したら、インポートするデータソースのデータの日付範囲を確認します。 既存のデータソースの範囲外のデータソースはインポートできません。レポートデータ

例えば、オンラインデータ追跡を実装する前のデータソースのデータを読み込むことはできません。 データソースのデータは日別に分類する必要があります。
