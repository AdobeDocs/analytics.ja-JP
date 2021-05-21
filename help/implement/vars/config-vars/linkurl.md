---
title: linkURL
description: AppMeasurement がリンクトラッキングコールで使用する、自動生成されたリンク URL を上書きします。
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '115'
ht-degree: 100%

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

[tl()](../functions/tl-method.md) メソッドの 3 番目の引数が設定されていない場合は、代わりに `linkURL` 変数が使用されます。
