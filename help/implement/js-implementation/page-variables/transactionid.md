---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# transactionID

[!UICONTROL 統合データソース]では、[!UICONTROL transactionID] を利用して、オフラインデータをオンライントランザクション（オンラインで生成されたリードや購入など）に関連付けます。


<!-- 

transactionID.xml

 -->

アドビに送信される一意の *`transactionID`* をイメージリクエストの一部として送信しておくことで、トランザクションに関するオフライン情報の[!UICONTROL データソース]を後日アップロードした際にオンラインデータとの紐付けが可能になります。[データソース](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)を参照してください。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | xact | 該当なし | "" |

**トランザクション ID ストレージの有効化**{#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

*`transactionID`* 変数が記録される前に、レポートスイートマネージャーで選択したレポートスイートの[!UICONTROL トランザクション ID ストレージ]を有効にしておく必要があります。この設定は、次の場所にあります。

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

*`transactionID Storage`* がレポートスイートに対して有効かどうかを確認するには、以下に移動しください。

```
Analytics > Admin > Data Sources > Manage
```

**構文と可能な値**{#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

*`transactionID`* には、英数字のみを使用できます。複数の [!UICONTROL transactionID] を 1 回のヒットで記録する場合、コンマを使用して複数の値を区切る必要があります。

**例** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**注意事項、質問、ヒント** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* *`transactionID`*&#x200B;の記録が有効になっていない場合、*`transactionID`* 値は破棄され、[!UICONTROL 統合データソース]で使用できなくなります。*`transactionID`* が設定されているページで、コンバージョン変数またはイベント（eVar またはイベント変数）を必ず設定するようにしてください。設定されていないと、*`transactionID`* にはデータは何も記録されません。

* 購入やリードなど、複数のシステムの [!UICONTROL transactionID] を記録する場合は、*`transactionID`* の値が常に一意であることを確認します。これは、lead_1234 や purchase_1234 のように、ID にプレフィックスを追加することで実現できます。*`transactionID`* が 2 回参照されると、[!UICONTROL 統合データソース]は正常に機能しません（[!UICONTROL データソース]のデータが間違ったデータと結び付けられます）。

* デフォルトでは、*`transactionID`* 変数の値は 90 日間記憶されます。オフラインのインタラクションプロセスが 90 日を超える場合は、カスタマーケアにご連絡いただき、限度を延長してください。

> [!NOTE]*`transactionID`* 変数には、コンマ以外の文字を含めることができます。文字制限（最大 100 バイト）が指定される場所に配置されます。マルチバイト文字が使用されている場合、transactionID に予期しない文字が含まれるという問題が発生しないように、マルチバイト文字のサポートを有効にする必要があります。*`transactionID`*（名前をつけて保存）する必要があります。
