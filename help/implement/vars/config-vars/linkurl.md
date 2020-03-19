---
title: linkURL
description: AppMeasurementがリンクトラッキングコールで使用する、自動生成されたリンクURLを上書きします。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkURL

リンクトラッキングコールがアドビに送信されるたびに、データ収集サーバーはURLを自動的に検出します。 変数を使用し `linkURL` て、検出されたURLを上書きします。

## Adobe Experience Platform LaunchでのURLのリンク

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.linkURLとカスタムコードエディターの起動

変数 `s.linkURL` は、リンクがクリックされたときのブラウザーのURLを含む文字列です。 この変数は、レポートで使用できるディメンションを入力しません。

```js
s.linkURL = "https://example.com";
```

変数がリ [`linkName`](linkname.md) ンクトラッキングコールに設定されていない場合は、代わりに変 `linkURL` 数が使用されます。
