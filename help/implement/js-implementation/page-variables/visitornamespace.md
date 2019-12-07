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


# visitorNamespace

 変数は、cookie が設定されているドメインを識別するために使用されます。


<!-- 

visitorNamespace.xml

 -->

*`visitorNamespace`* を JavaScript ファイルで設定している場合は、この変数を削除または変更しないでください。*`visitorNamespace`* を変更すると、Analytics でレポートされるすべての訪問者が新規訪問者となる場合があります。また、訪問者履歴が現在および今後のトラフィックから切り離されます。アドビの担当者の許可がない場合は、この変数を変更しないでください。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | ns | 該当なし | "" |

Analytics では、サイトへの訪問者を一意に識別するために cookie を使用します。*`visitorNamespace`* を使用しない場合、cookie は 2o7.net に関連付けられます。*`visitorNamespace`* を使用する場合、cookie は 2o7.net のサブドメインに関連付けられます。サイトへのすべての訪問者の cookie は同じドメインまたはサブドメインに関連付ける必要があります。

この  *`visitorNamespace`* 変数を使用するのは、ブラウザーの cookie 制限を超過しないようにするためです。Internet Explorer には、ドメインにつき 20 個の cookie までという制限があります。この *`visitorNamespace`* 変数を使用することによって、他社が使用している Analytics の cookie が貴社の訪問者の cookie と競合しなくなります。

**構文と可能な値** {#section_EE247FE371784CA4B6058182181F3EA1}

*`visitorNamespace`* の値は、アドビによって提供される必要があります。また、コンマ、ピリオド、スペース、特殊文字を含まない、ASCII 文字の文字列にする必要があります。

```js
s.visitorNamespace="company_specific_value"
```

**複数レポートスイートでの訪問者の識別** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

`visitorNamespace` を指定していない場合は、社内の各レポートスイートは「`s_vi_[random string]`」という形式の個別の訪問者 ID cookie を受信します。`visitorNamespace` を指定した場合は、指定した `s_vi` にデータを送信するすべてのレポートスイートで、同じ `trackingServer` cookie が使用されます。マルチスイートタギングを導入している場合は、各レポートスイートで同一の cookie が使用されるように訪問者の名前空間を指定してください。

**例** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**設定** {#section_1128A2531ECC43DFA6749ECC21F050A2}

なし
