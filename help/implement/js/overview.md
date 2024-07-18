---
title: JavaScriptのAppMeasurementを使用したAdobe Analyticsの実装
description: タグ管理システムなしで JavaScript を使用して Adobe Analytics を実装する方法を説明します。
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 42%

---

# JavaScriptのAppMeasurementを使用したAdobe Analyticsの実装

JavaScript 版 AppMeasurement は、これまで Adobe Analytics を実装する一般的な方法でした。ただし、Tag Management システムの人気が高まっており、[Adobe Experience Platform のタグ](../launch/overview.md) の使用がお勧めです。

実装タスクの大まかな概要：

![JavaScript 用のAppMeasurementを使用してAdobe分析を実装する方法については、この節で説明します。](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>タスク</b></th><th style="width:20%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td><td><b> レポートスイートを定義 </b> したことを確認します。</td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td><td><b>AppMeasurementに必要なJavaScript コードを Code Manager からダウンロードします </b>。 ファイルを解凍します。</td><td><a href="../../admin/admin/code-manager-admin.md">コードマネージャー</a></td>
</tr>

<tr>
<td>3</td><td><b>Web サイトのテンプレートファイルに <code>AppMeasurement.js</code> を追加します </b>。 このコードには、Adobeにデータを送信するために必要なライブラリが含まれています。

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b><code>AppMeasurement.js</code></b> 内で設定変数を定義します。 Analytics オブジェクトがインスタンス化されると、これらの変数によって、データ収集設定が正しいことが確認されます。

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">設定変数</a></td>
</tr>

<tr>
<td>5</td><td><b> サイトのページコード内でページレベル変数を定義します </b>。 これらの変数は、Adobeに送信される特定のディメンションと指標を決定します。

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">ページ変数</a></td>
</tr>

<tr>
<td>6</td><td><b> すべてのページ変数が定義されている場合、<code>t()</code> メソッドを使用してデータをAdobeに送信します </b>。

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t （） メソッド</a></td>
</tr>

<tr>
<td>7</td><td>実装を実稼動環境にプッシュする前に、<b>実装を拡張して検証します</b>。</b></td><td></td>
</tr>

</table>

## その他のリソース

- [変数、関数、メソッド、プラグインの概要](../vars/overview.md)
