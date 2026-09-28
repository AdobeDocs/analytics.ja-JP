---
title: モジュールの統合
description: 統合モジュールを使用すると、アドビパートナーは自社のデータ収集作業をお客様の組織と統合できます。
feature: Appmeasurement Implementation
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/4RfEY-mGPVvRz5OQuGe5DwoCKThVHtNf3pMUFfFzqoE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 98%
---
# モジュールの統合

統合モジュールを使用すると、アドビパートナーは自社のデータ収集作業をお客様の組織と統合できます。 この統合により、双方向のデータ接続の機会が得られます。 通常、統合モジュールの使用はアドビパートナーが主導します。

>[!NOTE]
>
>実装でパートナーデータをリクエストすると、ページ読み込みとアドビのデータ収集サーバーに送信されるデータの間に遅延が生じる可能性があります。 データの送信前に訪問者が新しいページを読み込んだ場合、そのページは記録されません。

## 統合モジュールのワークフロー

1. サイトの訪問者が、パートナーデータの `get` リクエストを開始するページを読み込みます。
2. アドビのパートナーが `get` 要求を受け取り、適切な変数を JSON オブジェクトにパッケージ化します。 JSON オブジェクトが返されます。
3. サイトが JSON オブジェクトを受け取り、`setVars` を呼び出して JSON オブジェクトに含まれる情報を Adobe Analytics 変数に割り当てます。
4. イメージリクエストがアドビデータ収集サーバーに送られます。

## 統合モジュールの実装

アドビパートナーと連携している組織は、これらの手順を使用して統合モジュールの使用を正常に開始できます。

### 統合モジュールコードの取得

モジュールコードを取得するには、Product Admin アクセス権を持つユーザー、または Code Manager へのアクセス権を持つ製品プロファイルに属するユーザーである必要があります。 モジュールコードの取得方法は、Adobe Experience Platform のタグを含め、すべての実装方法で同じです。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
1. 右上の 9 つの正方形のアイコン、色付きの Analytics ロゴの順にクリックします。
1. 上部のナビゲーションで、**[!UICONTROL 管理者]**／**[!UICONTROL すべての管理者]**／**[!UICONTROL Code Manager]** をクリックします。
1. 最新の JavaScript AppMeasurement ライブラリをダウンロードします。
1. ダウンロードが完了したら、ファイルを展開して `AppMeasurement_Module_Integrate.js` を見つけます。

### 実装に統合モジュールを配置する

サイトにIntegrate Moduleを実装するには、Adobe Experience Platform Data Collectionへのアクセスが必要です。 レガシー JavaScript 実装を使用する場合は、組織の Web サイトソースコードへのアクセスが必要になります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 編集するタグプロパティをクリックします。
1. 「拡張機能」タブをクリックしてから、Adobe Analytics で「設定」をクリックします。
1. 「カスタムコードを使用してトラッカーを設定」アコーディオンを開き、「&lt;/> エディターを開く」をクリックします。
1. 統合モジュールのコードをコードモーダルウィンドウに貼り付けます。 完了したら「保存」をクリックします。

## 統合モジュールのメソッド

統合モジュールが実装されたら、これらのメソッドを使用して、目的のアドビパートナーからデータを送受信するよう設定します。

### 追加

`add` メソッドはパートナーシステムと実装の間でデータを共有する際、変数データの中間記憶領域となる、パートナーオブジェクトをインスタンス化します。 このメソッドは、すべての統合に必要です。 1 件の実装で複数のパートナーを使用する場合は、各一意のパートナーごとに別個のパートナーオブジェクトを使用する必要があります。

```JavaScript
s.Integrate.add("<partner_name>");
```

通常、組織はアドビのパートナーと連携してパートナー名の値を決定します。

### beacon

`beacon` メソッドは、イメージリクエストを作成し、設定された URL を指します。 これらの画像リクエストは、標準的な画像リクエストとは異なります。 ビーコンメソッドは、通常、アドビのデータ収集サーバーではなく、アドビのパートナーにデータを送信します。

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

通常、組織はアドビのパートナーと連携してパートナー名の値を決定します。 URL に含まれるクエリ文字列はオプションで、パートナーに依存します。 ブラウザーのキャッシュを防ぐために、統合モジュールには乱数を含むクエリ文字列が自動的に含まれます。

### delay

アドビは、このメソッドを文書化するよう、社内チームと作業を進めています。

### get

`get` メソッドを使用すると、クライアントはパートナー変数を読み込み、パートナーオブジェクトに保存できます。 データがパートナーオブジェクトに含まれたら、Analytics 変数に割り当てられ、イメージリクエストで送信されます。 このメソッドは、目的のデータを含む JSON オブジェクトを指す URL を呼び出します。

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **パートナー名：**&#x200B;通常、組織はアドビのパートナーと連携してパートナー名の値を決定します。
* **JSON オブジェクトへの URL：**&#x200B;イメージリクエストに組み込むパートナー変数を含む JSON オブジェクトへの URL。
* **クエリ文字列パラメーター：**&#x200B;パートナーのシステム内で組織を識別するパートナーアカウント情報。 アドビパートナーは、この情報を使用してデータセットを識別します。

統合モジュールは、自動的に URL にクエリ文字列を追加します。 var クエリ文字列は、統合モジュールがパートナーから返されることを想定している JSON オブジェクトの名前を指定します。 また、ブラウザーのキャッシュを防ぐために、乱数も追加されます。

### Ready

アドビは、このメソッドを文書化するよう、社内チームと作業を進めています。

### useVars

`useVars` メソッドを使用すると、クライアントは変数の値をアドビのパートナーと共有できます。

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

通常、組織はアドビのパートナーと協力して、パートナー名およびパートナーが使用する変数の値を決定します。

### setVars

`setVars` メソッドを使用すると、クライアントは取得したパートナーデータを使用して Analytics 変数を設定できます。 パートナーデータは、`get` メソッド、静的割り当て、またはパートナーオブジェクトにデータを入力するその他のメカニズムの結果にすることができます。

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

通常、組織はアドビのパートナーと協力して、パートナー名およびパートナーが使用する変数の値を決定します。

### script

`script` メソッドを使用すれば、特定の条件が満たされた場合（例：campaign 変数が設定されている場合）に、アドビのパートナーがパートナーサイトから追加の JavaScript を呼び出すことができます。

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

通常、組織はアドビのパートナーと連携してパートナー名の値を決定します。 URL に含まれるクエリ文字列はオプションで、パートナーに依存します。 ブラウザーのキャッシュを防ぐために、統合モジュールには乱数を含むクエリ文字列が自動的に含まれます。
