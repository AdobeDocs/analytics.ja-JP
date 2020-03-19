---
title: JavaScript 版 AppMeasurement
description: タグ管理システムを使用せずに、JavaScriptを使用してAdobe Analyticsを実装する方法を説明します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# JavaScript 版 AppMeasurement

JavaScript版AppMeasurementは、これまで、Adobe Analyticsを実装する一般的な方法でした。 ただし、Tag Management Systemsの人気が高まるにつれ、 [Adobe Experience Platform Launchの使用をお勧めします](../launch/overview.md) 。

## JavaScriptを使用してアドビにデータを送信するワークフロー全体

1. ファイルを読み込 `AppMeasurement.js` みます。 このファイルには、アドビへのデータの送信に必要なライブラリが含まれています。

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. 内で設定変数を定義しま `AppMeasurement.js`す。 Analyticsオブジェクトがインスタンス化されるとき、これらの変数はデータ収集の設定が正しいことを確認します。 定義で [きる変数の完全なリストは](../vars/config-vars/configuration-variables.md) 、設定変数を参照してください。

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.omtrdc.net";
   ```

3. サイトのページコード内でページレベルの変数を定義します。 これらの変数は、アドビに送信される特定のディメンションと指標を決定します。 定義で [きる変数の完全なリストは](../vars/page-vars/page-variables.md) 、「ページ変数」を参照してください。

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. すべてのページレベル変数が定義されたら、このメソッドを使用してデータをアドビに送信 `t()` します。 詳しく [は](../vars/functions/t-method.md) 、tを参照してください。

   ```js
   s.t();
   ```
