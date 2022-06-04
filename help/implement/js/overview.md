---
title: JavaScript 版 AppMeasurement を使用したAdobe Analyticsの実装
description: タグ管理システムなしで JavaScript を使用して Adobe Analytics を実装する方法を説明します。
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
source-git-commit: 99fc7814eaa12d0d9e8e478629a4c2134a577aaa
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 91%

---

# JavaScript 版 AppMeasurement を使用したAdobe Analyticsの実装

JavaScript 版 AppMeasurement は、これまで Adobe Analytics を実装する一般的な方法でした。ただし、Tag Management システムの人気が高まっており、[Adobe Experience Platform のタグ](../launch/overview.md) の使用がお勧めです。

## JavaScript を使用したアドビへのデータ送信のワークフロー全体

1. `AppMeasurement.js` ファイルを読み込みます。このファイルには、アドビへのデータの送信に必要なライブラリが含まれています。

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. `AppMeasurement.js` で設定変数を定義します。Analytics オブジェクトがインスタンス化されるとき、これらの変数はデータ収集の設定が正しいことを確認します。定義できる変数の完全なリストについては、[設定変数](../vars/config-vars/configuration-variables.md)を参照してください。

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. サイトのページコード内でページレベルの変数を定義します。これらの変数は、アドビに送信される特定のディメンションと指標を決定します。定義できる変数の完全なリストについては、[ページ変数](../vars/page-vars/page-variables.md)を参照してください。

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. すべてのページレベル変数が定義されたら、`t()` メソッドを使用してデータをアドビに送信します。詳しくは、[t](../vars/functions/t-method.md) を参照してください。

   ```js
   s.t();
   ```
