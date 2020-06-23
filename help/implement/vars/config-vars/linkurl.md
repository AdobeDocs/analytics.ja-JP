---
title: linkURL
description: AppMeasurement がリンクトラッキングコールで使用する、自動生成されたリンク URL を上書きします。
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkURL

リンクトラッキングコールがアドビに送信されるたびに、データ収集サーバーは URL を自動的に検出します。`linkURL` 変数は、検出された URL を上書きするために使用します。

## Adobe Experience Platform Launch でのリンク URL

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.linkURL

`s.linkURL` 変数は、リンクがクリックされたときのブラウザー URL を含む文字列です。この変数は、レポートで使用できるディメンションを入力しません。

```js
s.linkURL = "https://example.com";
```

[`linkName`](linkname.md) 変数がリンクトラッキングコールに設定されていない場合は、代わりに `linkURL` 変数が使用されます。
