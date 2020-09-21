---
title: JavaScript 実装のトラブルシューティング
description: JavaScript 実装の一般的な問題とトラブルシューティングに関するベストプラクティスについて説明します。
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '694'
ht-degree: 100%

---


# JavaScript 実装のトラブルシューティング

組織が Adobe Analytics にデータを正しく取り込めないいくつかの理由を次に示します。

## 引用符の使用

アドビに送信される変数のほとんどは文字列です。JavaScript では、一重引用符または二重引用符を使用できます。

### 変数を定義する引用符の混合

ベストプラクティスとして、使用する引用符の種類に一貫性があることを確認してください。一重引用符で文字列の開始を指定する場合は、一重引用符を使用して文字列を閉じる必要があります。

例えば、`s.eVar1 = 'Value'` と `s.eVar1 = "Value"` は両方とも有効です。`s.eVar1 = 'Value"` は無効です.

### 文字列への一重引用符または二重引用符の含め方

文字列に一重引用符または二重引用符を含めることもできます。例えば、レポートに `Alex's sale` や `John the "Hunter"` の値を含めるとします。これらの値を含める方法は 2 つあります。

* **他の引用符タイプを使用します**：例えば、`s.eVar1 = "Alex's sale"` と `s.eVar1 = 'John the "Hunter"'` は両方とも有効です。
* **エスケープ引用符**：バックスラッシュを使用して引用符をエスケープします。例えば、`s.eVar1 = 'Alex\'s sale'` と `s.eVar1 = "John the \"Hunter\""` は両方とも有効です。

### 中括弧の使用は避ける

一部のプログラムでは、中立引用符（`"..."` および `'...'`）が中括弧（`“...”` および `‘...’`）に自動的に変換されます。ドキュメントエディター（Microsoft Word など）の使用や、コードスニペットの電子メール送信は避けてください。中括弧は JavaScript では使用できません。

## Analytics オブジェクトの参照

アドビに送信されるすべての変数は、Analytics オブジェクトを使用します。ほとんどの実装では、`s` オブジェクトが使用されます。参照に Analytics オブジェクトを含む変数を参照する場合は、必ず変数を参照してください。

例えば、`s.eVar1 = 'Value'` は有効ですが、`eVar1 = 'Value'` は無効です。

## 各変数を 1 回定義します。

追跡関数（`s.t()`）が実行されると、AppMeasurement は定義済みのすべての変数を取得し、それらをイメージリクエストにコンパイルします。実装で変数を複数回定義した場合は、最新の値のみが使用されます。追跡関数を実行する際は、すべての変数値に正しい値が含まれていることを確認してください。

## 変数の大文字/小文字の正しさ

一部の変数では大文字を使用します。JavaScript 変数では大文字と小文字が区別されます。変数を定義する際は、必ず正しいケースを使用してください。例えば、`s.eVar1 = 'Value'` は有効ですが、`s.evar1 = 'Value'` は無効です。

## プラグイン

一部の組織では、Adobe Analytics の実装を改善するためにプラグインを使用しています。AppMeasurement バージョンをアップグレードする場合は、インストール済みのプラグインを必ず再び含めてください。[!UICONTROL Code Manager] で作成されたコードには、そのコードに含まれるプラグインコードはありません。AppMeasurement の以前のバージョンに戻す必要が生じた場合に備えて、既存のコードのコピーを作成します。

## 変数値での空白

HTML には、空白を作成するための文字が複数あります。これらには、スペース、タブ、およびキャリッジリターン（またはラインフィード）が含まれます。次の例をご覧ください。

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

この場合、`document.title` が `s.pageName` に設定されて、「Home Page」の値を受け取ります。ただし、一部のブラウザーでは、空白の解釈が異なる場合があります。結果は、次の 2 つの例のいずれかになります。

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

これらの 2 つの変数値は、Adobe Analytics では別々の値と見なされます。ただし、空白は表示のために自動的に削除されます。結果として、「ホームページ」の行項目が 2 つ表示されます。変数値に、目的の値の前後に空白が含まれていないことを確認します。

## 切り捨てられたイメージリクエスト

多くの変数に長い値を設定する実装では、イメージリクエストが切り捨てられる場合があります。Internet Explorer など、一部の古いブラウザーでは、イメージリクエスト URL に 2083 文字の制限が設けられています。組織が非常に長いイメージリクエストを扱う場合は、次の操作を試してください。

* **Experience Cloud ID サービスの使用**：AppMeasurement ライブラリ 1.4.1 以降では、イメージリクエストが長すぎる場合、送信に自動的に HTTP POST を使用します。このメソッドを使用して送信されるデータは、長さに関係なく切り捨てられません。詳しくは、[Adobe Experience Cloud ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を参照してください。
* **処理ルールの使用**：[処理ルール](/help/admin/admin/c-processing-rules/processing-rules.md)では、変数間で値をコピーできます。この方法を使用すると、複数の変数で同じ値を設定する手間を省くことができます。次に例を示します。

   常に実行：<br>prop1 の値を eVar1 で上書き<br>eVar2 の値を eVar1 で上書き<br>prop2 の値を eVar1 で上書き<br>

   次に、実装に eVar1 を設定します。

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   ```

* **動的変数の使用**：実装で多くの変数に同じ値が設定される場合、[動的変数](/help/implement/vars/page-vars/dynamic-variables.md)を使用して、リクエスト URL を短縮できます。

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   s.eVar2 = "D=v1";
   s.prop1 = "D=v1";
   s.prop2 = "D=v1";
   ```

* **分類の使用**：製品名やページ名が非常に長い場合は、識別値やコードを使用し、[分類](/help/components/classifications/c-classifications.md)を使用してわかりやすい名前を表示できます。
