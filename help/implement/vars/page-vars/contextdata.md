---
title: contextData
description: コンテキストデータ変数を使用すると、処理ルールで読み取ることのできる各ページにカスタム変数を定義できます。
feature: Appmeasurement Implementation
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
TQID: https://experienceleague.adobe.com/Axaq7Rm6Ep2dyzjtWJAKLoOgG1iCt4QWuxf6H0fS75U
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 601
ht-degree: 64%

---

# contextData

コンテキストデータ変数を使用すると、処理ルールで読み取ることのできる各ページにカスタム変数を定義できます。 コード内の Analytics 変数に値を明示的に割り当てる代わりに、コンテキストデータ変数でデータを送信できます。 次に、処理ルールは、コンテキストデータ変数の値を取得し、それぞれの Analytics 変数に渡します。 『管理ユーザガイド』の「[処理ルール](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)」を参照してください。

コンテキストデータ変数は、開発チームが番号付き変数ではなく名前付きの要素でデータを収集する場合に役立ちます。 例えば、開発チームにページの作成者の `eVar10` への割り当てをリクエストする代わりに、`s.contextData["author"]` への割り当てをリクエストできます。 その後、組織の Analytics 管理者は、コンテキストデータ変数をレポート用の Analytics 変数にマップする処理ルールを作成できます。 最終的には、Adobeで提供される多くのページ変数ではなく、コンテキストデータ変数のみを使用することになります。

すべてのコンテキストデータ変数（キーと値を含む）の最大サイズは32 KBです。

## Web SDK を使用したコンテキストデータ変数

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;を使用する場合、Adobe Analytics変数にマッピングされないすべてのフィールドがコンテキストデータ変数として自動的に含まれます。 また、XDM オブジェクトを使用してコンテキストデータを明示的に設定することもできます。 次に、[処理ルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)を使用して、コンテキストデータ変数を目的のAnalytics変数に割り当てることができます。  詳しくは、[他のXDM フィールドをAnalytics変数にマッピング &#x200B;](../../aep-edge/xdm-var-mapping.md#mapping-other-xdm-fields-to-analytics-variables)を参照してください。

[**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)&#x200B;を使用する場合、すべてのコンテキストデータ変数はキーと値のペアとして`data.__adobe.analytics.contextData`内に存在します。

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

[処理ルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) インターフェイスには、該当するドロップダウンメニューに`example_variable`と`second_example`が表示されます。

## Adobe Analytics 拡張機能を使用したコンテキストデータ変数

Adobe Experience Platform データ収集には、コンテキストデータ変数を設定するための専用の場所がありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.contextData

`s.contextData` 変数は値を直接取りません。 代わりに、この変数のプロパティを文字列に設定します。

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* 有効なコンテキストデータ変数には、英数字、アンダースコアおよびピリオドのみが含まれます。 ハイフンなどの他の文字を含める場合、処理ルールでのデータ収集は保証されません。
* コンテキストデータ変数を`"a."`のプレフィックスで開始しないでください。 この接頭辞はアドビが予約して使用します。 例えば、`s.contextData["a.InstallEvent"]` を使用しないでください。
* コンテキストデータ変数では、大文字と小文字が区別されません。 `s.contextData["example"]` 変数と `s.contextData["EXAMPLE"]` 変数は同じです。
* 1つのキーに複数の値を含めることはできません。 複数値の変数にコンテキストデータ変数を使用する場合は、区切り文字（通常はコンマ）を使用してすべての値を連結し、処理ルールを使用して[&#x200B; リスト prop](prop.md#list-props)または[&#x200B; リスト変数](list.md)のいずれかに渡します。

## 処理ルールを使用した Analytics 変数の入力

>[!WARNING]
>
>コンテキストデータ変数は、処理ルールの実行後に破棄されます。 変数に値を配置する処理ルールがアクティブでない場合、そのデータは永久的に失われます。

1. コンテキストデータ変数の名前と値を設定するには、実装を更新します。
2. Adobe Analyticsにログインし、**[!UICONTROL Admin]** > **[!UICONTROL Report]** Suitesに移動します。
3. 目的のレポートスイートを選択し、**[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL 処理ルール]**&#x200B;に移動します。
4. Analytics 変数をコンテキストデータ変数値に設定する処理ルールを作成します。
5. 変更を保存します。

処理ルールは、保存するとすぐに有効になります。 履歴データには適用されません。

## リンクトラッキングコールでのコンテキストデータの送信

コンテキストデータ変数を `contextData` のプロパティとして [`s.linkTrackVars`](../config-vars/linktrackvars.md) に含めます。

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## コンテキストデータ変数を使用したイベントの増分

処理ルールを作成する際に、コンテキストデータ変数をイベントに割り当てることができます。

* コンテキストデータ変数に任意の種類のテキストが含まれている場合、イベント値は 1 ずつ増分されます。
* コンテキストデータ変数に整数が含まれる場合、イベントはその整数分だけ増加します。

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
