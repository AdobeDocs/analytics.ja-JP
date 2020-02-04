---
title: linkURL
description: AppMeasurementがリンクトラッキングコールで使用する、自動生成されたリンクURLを上書きします。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkURL

リンクトラッキングコールがアドビに送信されるたびに、データ収集サーバーはURLを自動的に検出します。 この変数を使 `linkURL` 用して、検出されたURLを上書きします。

## Adobe Experience Platform LaunchでのリンクURL

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.linkURLとカスタムコードエディターの起動

変数 `s.linkURL` は、リンクがクリックされたときのブラウザーのURLを含む文字列です。 この変数は、レポートで使用できるディメンションを入力しません。

```js
s.linkURL = "https://example.com";
```

変数がリ `linkName` ンクトラッキングコールに設定されていない場合は、代わりに `linkURL` その変数が使用されます。
