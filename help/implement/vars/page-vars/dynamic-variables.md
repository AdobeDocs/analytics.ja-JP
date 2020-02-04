---
title: 動的変数
description: イメージリクエストの長さを増やさずに変数をコピーします。
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# 動的変数

動的変数を使用すると、イメージリクエストの長さを増やすことなく、変数間で値をコピーできます。 複数の変数で同じデータを取り込む場合に便利です。

以前のバージョンのAnalyticsでは、データが切り捨てられるのを防ぐために、イメージリクエストの長さが重要でした。 AppMeasurementの改善により、イメージリクエストのクエリ文字列を大幅に長くすることができるので、通常、動的変数は不要です。

動的変数は、イメージリクエスト内のクエリ文字列パラメーターまたはHTTPヘッダーをサポートします。 参照可能 [なパラメーターの完全なリストについては](../../validate/query-parameters.md) 、「データ収集クエリーパラメーター」を参照してください。 参照可能 [なHTTP要求フィールドの一覧については](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) 、Wikipediaの「標準要求フィールド」を参照してください。

動的変数のプレフィックスが認識されると、レポートスイートのクエリ文字列またはHTTPヘッダー値が自動的にコピーされます。 このアクションは、処理ルールやVISTAルールなど、他の処理の前に発生します。

> [!TIP] 変数をコピーする際は、文字制限の最大値に注意してください。 例えば、にコピーする場 `eVar1` 合、100バ `prop1`イトの制限（255バイトの制限）があるので、切り捨てら `prop1``eVar1` れた値が含まれる可能性があります。

## Adobe Experience Platform Launchの動的変数

動的変数は、文字列を受け取る任意のディメンションフィールドで使用できます。 ディメンション値は、通常、Analytics拡張（グローバル変数）の設定時またはルールで設定されます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 目的のディメンション値を見つけます。

テキストフィールドに動的変数のプレフィックスを配置し、参照するクエリ文字列パラメーターまたはHTTPヘッダーを指定します。 デフォルトでは、動的変数のプレフィックスはで `D=`す。

## AppMeasurementの動的変数およびカスタムコードエディターの起動

動的変数は、他の変数に割り当てられるテキスト文字列です。 動的変数のデフォルトのプレフィックスはで `D=`す。 動的変数では大文字と小文字が区別されます。

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

> [!NOTE] 動的変数は、実装のデバッグ時に文字列として表示されます。 値は、アドビのデータ収集サーバーによってサーバー側でコピーされます。
