---
title: 動的変数
description: イメージリクエストの長さを増やさずに変数をコピーします。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '359'
ht-degree: 100%

---


# 動的変数

動的変数を使用すると、イメージリクエストの長さを増やすことなく、変数間で値をコピーできます。複数の変数で同じデータを取り込む場合に便利です。

以前のバージョンの Analytics では、データが切り捨てられるのを防ぐために、イメージリクエストの長さが重要でした。AppMeasurement の改善により、イメージリクエストのクエリー文字列を大幅に長くすることができるので、通常、動的変数は不要です。

動的変数は、イメージリクエスト内のクエリー文字列パラメーターまたは HTTP ヘッダーをサポートします。参照可能なパラメーターの完全なリストについては、[データ収集クエリーパラメーター](../../validate/query-parameters.md)を参照してください。参照可能な HTTP 要求フィールドの完全なリストについては、Wikipedia の [Standard request fields](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields)（英語）を参照してください。

動的変数のプレフィックスが認識されると、レポートスイートのクエリー文字列または HTTP ヘッダー値が自動的にコピーされます。このアクションは、処理ルールや VISTA ルールなど、他の処理の前に発生します。

>[!TIP]
>
> 変数をコピーする際は、文字制限の最大値に注意してください。例えば、`eVar1` を `prop1` にコピーする場合、100 バイトの上限（`eVar1` の上限は 255 バイト）があるので、`prop1` に切り捨てられた値が含まれる可能性があります。

## Adobe Experience Platform Launch の動的変数

動的変数は、文字列を受け取る任意のディメンションフィールドで使用できます。ディメンションこう項目は、通常、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定されます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. 目的のディメンション項目を見つけます。

テキストフィールドに動的変数のプレフィックスを配置し、参照するクエリー文字列パラメーターまたは HTTP ヘッダーを指定します。デフォルトでは、動的変数のプレフィックスは `D=` です。

## AppMeasurement および Launch カスタムコードエディターの動的変数

動的変数は、他の変数に割り当てられるテキスト文字列です。動的変数のデフォルトのプレフィックスは `D=` です。動的変数では大文字と小文字が区別されます。

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
> 動的変数は、実装のデバッグ時に文字列として表示されます。値は、アドビのデータ収集サーバーによってサーバー側でコピーされます。
