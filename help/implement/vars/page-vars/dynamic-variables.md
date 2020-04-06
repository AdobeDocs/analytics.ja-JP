---
title: 動的変数
description: イメージリクエストの長さを増やさずに変数をコピーします。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 動的変数

動的変数を使用すると、イメージリクエストの長さを増やすことなく、変数間で値をコピーできます。複数の変数で同じデータを取り込む場合に便利です。

以前のバージョンの Analytics では、データが切り捨てられるのを防ぐために、イメージリクエストの長さが重要でした。AppMeasurement の改善により、イメージリクエストのクエリー文字列を大幅に長くすることができるので、通常、動的変数は不要です。

動的変数は、イメージリクエスト内のクエリー文字列パラメーターまたは HTTP ヘッダーをサポートします。参照可能なパラメーターの完全なリストについては、[データ収集クエリーパラメーター](../../validate/query-parameters.md)を参照してください。参照可能な HTTP 要求フィールドの完全なリストについては、Wikipedia の [Standard request fields](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields)（英語）を参照してください。

動的変数のプレフィックスが認識されると、レポートスイートのクエリー文字列または HTTP ヘッダー値が自動的にコピーされます。このアクションは、処理ルールや VISTA ルールなど、他の処理の前に発生します。

>[!TIP] 変数をコピーする際は、文字制限の最大値に注意してください。例えば、`eVar1` を `prop1` にコピーする場合、100 バイトの上限（`eVar1` の上限は 255 バイト）があるので、`prop1` に切り捨てられた値が含まれる可能性があります。

## Adobe Experience Platform Launch の動的変数

動的変数は、文字列を受け取る任意のディメンションフィールドで使用できます。ディメンション値は、通常、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定されます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. 目的のディメンション値を見つけます。

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

>[!NOTE] 動的変数は、実装のデバッグ時に文字列として表示されます。値は、アドビのデータ収集サーバーによってサーバー側でコピーされます。
