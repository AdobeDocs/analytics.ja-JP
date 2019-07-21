---
title: Integrate Module
seo-title: Adobe Analytics用統合モジュール
description: Integrateモジュールを使用すると、アドビパートナーはデータ収集活動を組織に統合できます。
seo-description: Integrateモジュールを使用すると、アドビパートナーはデータ収集活動を組織に統合できます。
translation-type: tm+mt
source-git-commit: dae73042ace20eded9d0caf690a14203827f903a

---


# Integrate Module

Integrateモジュールを使用すると、アドビパートナーはデータ収集活動を組織に統合できます。この統合により、双方向のデータ接続を実現できます。一般に、Integrateモジュールの使用はアドビパートナーによって実行されます。

> [!NOTE] 導入でパートナーデータをリクエストすると、ページの読み込みとAdobeデータ収集サーバーに送信されるデータの間の遅延が増える可能性があります。訪問者がデータを送信する前に新しいページを読み込むと、そのページは記録されません。

## Integrateモジュールのワークフロー

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. JSONオブジェクトが返されます。
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. イメージリクエストがアドビデータ収集サーバーに送られます。

## Integrateモジュールの実装

アドビパートナーと作業している組織は、これらの手順を使用して統合モジュールの使用を正常に開始できます。

### 統合モジュールコードの取得

モジュールコードの取得には、製品管理者アクセス権を持つユーザー、またはコードマネージャーへのアクセス権を持つ製品プロファイルに属している必要があります。モジュールコードを取得する方法は、Adobe Experience Platform Launchなどのすべての実装方法で同じです。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. 右上の9正方形アイコンをクリックし、色付きのAnalyticsロゴをクリックします。
1. In the top navigation, click [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. 最新のJavaScript AppMeasurementライブラリをダウンロードします。
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### 統合モジュールを実装に配置する

サイトへの統合モジュールの実装には、Adobe Experience Platform Launchへのアクセスが必要です。従来のJavaScript実装を使用する場合、組織のWebサイトソースコードにアクセスする必要があります。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. 編集する起動プロパティをクリックします。
3. 「拡張機能」タブをクリックし、"Adobe Analyticsの設定」をクリックします。
4. 「カスタムコードを使用してトラッカーを設定」を開き、"&lt;/&gt;エディターを開く」をクリックします。
5. 統合モジュールコードをコードモーダルウィンドウに貼り付けます。完了したら「保存」をクリックします。

## Integrateモジュールメソッド

統合モジュールが導入されたら、これらのメソッドを使用して、目的のアドビパートナーからデータを送受信するように設定します。

### add

`add` このメソッドはパートナーオブジェクトをインスタンス化します。パートナーオブジェクトは、パートナーシステムと実装間でデータを共有するときに、変数データの中間ストアとして機能します。このメソッドは、すべての統合に必要です。単一の実装で複数のパートナーが使用されている場合、個別のパートナーオブジェクトを個別のパートナーに使用する必要があります。

```JavaScript
s.Integrate.add("<partner_name>");
```

組織は通常、パートナー名の値を決定するためにアドビパートナーと連携します。

### ビーコン

`beacon` このメソッドはイメージリクエストを作成し、指定されたURLをポイントします。これらのイメージリクエストは、標準的なイメージリクエストとは異なります。ビーコンメソッドは通常、Adobeのデータ収集サーバーではなく、アドビパートナーにデータを送信します。

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

組織は通常、パートナー名の値を決定するためにアドビパートナーと連携します。URLに含まれるクエリ文字列はオプションで、パートナーに依存しています。Integrateモジュールには、ブラウザーのキャッシュを防ぐために乱数を含むクエリ文字列が自動的に含まれています。

### delay

アドビでは、内部でチームと連携して、この方法について説明しています。

### get

`get` この方法により、クライアントはパートナー変数をインポートしてパートナーオブジェクトに保存できます。パートナーオブジェクトにデータがあると、Analytics変数に割り当ててイメージリクエストで送信できます。このメソッドは、目的のデータを含むJSONオブジェクトをポイントするURLを呼び出します。

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **パートナー名:** 組織は通常、パートナー名の値を決定するためにアドビパートナーと連携します。
* **URL to JSON object:** イメージリクエストに組み込むパートナー変数を含むJSONオブジェクトへのURLです。
* **クエリ文字列パラメータ:** パートナーのシステム内で組織を識別するパートナーアカウント情報。アドビパートナーは、この情報を使用してデータセットを特定します。

Integrateモジュールは、URLにクエリ文字列を自動的に追加します。varクエリ文字列は、パートナーからのバックフォームであるJSONオブジェクトの名前を指定します。ブラウザーのキャッシュを防ぐために乱数も追加されます。

### ready

アドビでは、内部でチームと連携して、この方法について説明しています。

### useVars

`useVars` この方法により、クライアントはアドビパートナーと変数の値を共有できます。

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

組織は通常、パートナー名とパートナーが使用する変数の値を決定するために、アドビパートナーと連携します。

### setVars

`setVars` このメソッドを使用すると、クライアントは取得したパートナーデータを使用してAnalytics変数を入力できます。Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

組織は通常、パートナー名とパートナーが使用する変数の値を決定するために、アドビパートナーと連携します。

### script

`script` このメソッドにより、Adobeパートナーは特定の条件に一致する場合（例えば、キャンペーン変数が設定されている場合など）、パートナーサイトから追加のJavaScriptを呼び出すことができます。

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

組織は通常、パートナー名の値を決定するためにアドビパートナーと連携します。URLに含まれるクエリ文字列はオプションで、パートナーに依存しています。Integrateモジュールには、ブラウザーのキャッシュを防ぐために乱数を含むクエリ文字列が自動的に含まれています。
