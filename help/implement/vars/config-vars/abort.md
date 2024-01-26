---
title: abort
description: abort 変数は、ヒットがアドビのデータ収集サーバーに送信されないようにするブール値です。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 44%

---

# abort

The `abort` 変数は、次のトラッキングコールがAdobeに送信されるのを防ぐことができるブール値です。 Web SDK にも同様の機能があり、 `false` XDM イベントの送信前に設定されます。

## Web SDK 拡張機能を使用したイベントの送信のキャンセル

以下を使用します。 [!UICONTROL イベント送信前のコールバック時] コードエディターと戻る `false`.

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. の下 [!UICONTROL データ収集]をクリックし、 **[!UICONTROL イベント送信コールバックコードの前に編集]** 」ボタンをクリックします。
1. コードエディターで、Edge へのデータ送信を中止する場合は、次のコードを配置します。

```js
return false;
```

## Web SDK を手動で実装するイベントの送信のキャンセル

以下を使用します。 `onBeforeEventSend` コールバックと return `false`. 詳しくは、 [イベントのグローバルな変更](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) （ Web SDK ドキュメント）を参照してください。

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Adobe Analytics拡張機能での abort 変数の使用

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## s.abort inAppMeasurementと Analytics 拡張機能のカスタムコードエディター

`s.abort` 変数はブール値です。デフォルト値は `false` です。

* `true` に設定した場合、次のトラッキングコール（[`t()`](../functions/t-method.md) または [`tl()`](../functions/tl-method.md)）はデータをアドビに送信しません。
* `false` に設定した場合、または定義しなかった場合、この変数は何もしません。

```js
s.abort = true;
```

>[!NOTE]
>
> `abort` 変数は、トラッキングコールのたびに `false` にリセットされます。同じページで後続のトラッキングコールを中止する必要がある場合は、`abort` を再度 `true` に設定します。

例えば、 `abort` 変数は、 [`doPlugins()`](../functions/doplugins.md) 関数内で使用されます。これは、イメージリクエストがAdobeに送信される前に実行される最後の関数です。 この例の動作は、 `onBeforeEventSend` Web SDK を使用したコールバック。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

追跡したくないアクティビティ（ディスプレイ広告内の一部のカスタムリンクや外部リンクなど）の識別に使用するロジックを一元管理することができます。
