---
title: JavaScript 版 AppMeasurement を使用した Adobe Analytics の実装
description: タグ管理システムなしで JavaScript を使用して Adobe Analytics を実装する方法について説明します。
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
TQID: https://experienceleague.adobe.com/QScNJBw6-Xn-gQCJBBxVT6melUpnyy6VIKrzvnDzJyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 100%

---

# JavaScript 版 AppMeasurement を使用した Adobe Analytics の実装

JavaScript 版 AppMeasurement は、これまで Adobe Analytics を実装する一般的な方法でした。 ただし、Tag Management システムの人気が高まっており、[Adobe Experience Platform のタグ](../launch/overview.md) の使用がお勧めです。

実装タスクの大まかな概要：

![JavaScript 版 AppMeasurement を使用した Adobe Analytics の実装について詳しくは、この節を参照してください。](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>タスク</b></th><th style="width:20%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td><td><b>レポートスイートを定義</b>したことを確認します</td><td><a href="../../admin/tools/manage-rs/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td><td>Code Manager から <b>AppMeasurement に必要な JavaScript コードをダウンロード</b>します。 ファイルを ZIP 解凍します。</td><td><a href="../../admin/tools/code-manager-admin.md">Code Manager</a></td>
</tr>

<tr>
<td>3</td><td><b><code>AppMeasurement.js</code> を web サイトのテンプレートファイルに追加します</b>。 このコードには、アドビへのデータの送信に必要なライブラリが含まれています。

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b><code>AppMeasurement.js</code></b> で設定変数を定義します。 Analytics オブジェクトがインスタンス化されるとき、これらの変数はデータ収集の設定が正しいことを確認します。

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
<td>5</td><td><b>サイトのページコード内でページレベルの変数を定義します</b>。 これらの変数は、アドビに送信される特定のディメンションと指標を決定します。

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">ページ変数</a></td>
</tr>

<tr>
<td>6</td><td>すべてのページ変数が定義されている場合は、<b><code>t()</code> メソッドを使用してデータをアドビに送信します</b>。

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t() メソッド</a></td>
</tr>

<tr>
<td>7</td><td>実装を実稼動環境にプッシュする前に、<b>実装を拡張して検証します</b>。</b></td><td></td>
</tr>

</table>

## その他のリソース

- [変数、関数、メソッド、プラグインの概要](../vars/overview.md)
