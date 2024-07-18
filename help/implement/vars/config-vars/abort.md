---
title: abort
description: abort 変数は、ヒットがアドビのデータ収集サーバーに送信されないようにするブール値です。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 39%

---

# abort

`abort` 変数はブール値で、次のトラッキングコールがAdobeに送信されるのを防ぐことができます。 Web SDK にも同様の機能があり、XDM イベントが送信される前に `false` を返すことができます。

## Web SDK 拡張機能を使用したイベントの送信のキャンセル

イベント送信コールバックの前に [!UICONTROL On] コードエディターを使用し、`false` を返します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL  拡張機能 ]」タブに移動し、「{4 **[!UICONTROL Adobe Experience Platform Web SDK]」の下にある「設定]** ボタンをクリックします。[!UICONTROL 
1. [!UICONTROL  データ収集 ] の下の **[!UICONTROL イベント送信前に編集コールバックコード]** ボタンをクリックします。
1. コードエディターで、Edgeへのデータ送信を中止する条件の下に次のコードを配置します。

```js
return false;
```

## Web SDK を手動で実装したイベントの送信のキャンセル

`onBeforeEventSend` コールバックを使用して、`false` を返します。 詳しくは、Web SDK ドキュメントの [ イベントのグローバルな変更 ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) を参照してください。

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Adobe Analytics拡張機能の abort 変数の使用

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementでの s.abort と Analytics 拡張機能のカスタムコードエディター

`s.abort` 変数はブール値です。デフォルト値は `false` です。

* `true` に設定した場合、次のトラッキングコール（[`t()`](../functions/t-method.md) または [`tl()`](../functions/tl-method.md)）はデータをアドビに送信しません。
* `false` に設定した場合、または定義しなかった場合、この変数は何もしません。

```js
s.abort = true;
```

>[!NOTE]
>
> `abort` 変数は、トラッキングコールのたびに `false` にリセットされます。同じページ上の後続のトラッキングコールを中止する場合は、`abort` を再度 `true` に設定します。

`abort` 変数は、イメージリクエストがAdobeに送信される前に実行する最後の関数である [`doPlugins()`](../functions/doplugins.md) 関数で設定できます。 この例は、Web SDK を使用した `onBeforeEventSend` コールバックと同様に動作します。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

追跡したくないアクティビティ（ディスプレイ広告内の一部のカスタムリンクや外部リンクなど）の識別に使用するロジックを一元管理することができます。
