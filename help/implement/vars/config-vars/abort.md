---
title: abort
description: abort 変数は、ヒットがアドビのデータ収集サーバーに送信されないようにするブール値です。
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
autotag-review: '2026-05-22T07:53:09.657Z'
TQID: 'https://experienceleague.adobe.com/3RASISgJtY29aSGrGzO7070ZyH-B5cl3Cgv3aN7xjEU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 343
ht-degree: 39%

---

# abort

`abort`変数は、次のトラッキング呼び出しがAdobeに送信されるのを防ぐことができるブール値です。 Web SDKにも同様の機能があり、XDM イベントが送信される前に`false`を返すことができます。

## Web SDK拡張機能を使用したイベントの送信をキャンセル

イベント送信前に[!UICONTROL On コールバック &#x200B;] コードエディターを使用して`false`を返します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. [!UICONTROL 拡張機能] タブに移動し、[!UICONTROL Adobe Experience Platform Web SDK]の下にある&#x200B;**[!UICONTROL Configure]** ボタンをクリックします。
1. [!UICONTROL &#x200B; データ収集]で、「**[!UICONTROL イベント送信前に編集」コールバックコード]** ボタンをクリックします。
1. コードエディターで、Edgeへのデータの送信を中止する条件で、次のコードを入力します。

```js
return false;
```

## Web SDKを手動で実装するイベントの送信をキャンセル

`onBeforeEventSend` コールバックを使用して、`false`を返します。 詳しくは、Web SDK ドキュメントの「[&#x200B; グローバルにイベントを変更する](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja#modifying-events-globally)」を参照してください。

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Adobe Analytics拡張機能でのabort変数の使用

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.abortとAnalytics拡張機能のカスタムコードエディター

`s.abort` 変数はブール値です。 デフォルト値は `false` です。

* `true` に設定した場合、次のトラッキングコール（[`t()`](../functions/t-method.md) または [`tl()`](../functions/tl-method.md)）はデータをアドビに送信しません。
* `false` に設定した場合、または定義しなかった場合、この変数は何もしません。

```js
s.abort = true;
```

>[!NOTE]
>
>`abort` 変数は、トラッキングコールのたびに `false` にリセットされます。 同じページで後続のトラッキング呼び出しを中止する場合は、もう一度`abort`を`true`に設定します。

`abort`変数は、[`doPlugins()`](../functions/doplugins.md)関数で設定できます。これは、イメージリクエストがAdobeに送信される前に実行する最後の関数です。 この例は、Web SDKを使用した`onBeforeEventSend` コールバックと同様に動作します。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

追跡したくないアクティビティ（ディスプレイ広告内の一部のカスタムリンクや外部リンクなど）の識別に使用するロジックを一元管理することができます。
