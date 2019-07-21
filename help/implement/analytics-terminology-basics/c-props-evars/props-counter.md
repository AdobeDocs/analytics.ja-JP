---
description: カウンターによって、特定のイベントまたはプロセスが発生した回数が保存（場合によっては表示）されます。
keywords: Analyticsの導入;props;s. prop;カスタムトラフィック、カウンター
seo-description: カウンターによって、特定のイベントまたはプロセスが発生した回数が保存（場合によっては表示）されます。
seo-title: カウンターとしてのpropの使用
solution: Analytics
title: カウンターとしてのpropの使用
topic: 開発者と導入
uuid: ab83bd7e-10d9-49f9- b9e7- c50397e95c17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# カウンターとしてのpropの使用

カウンターによって、特定のイベントまたはプロセスが発生した回数が保存（場合によっては表示）されます。

prop を使用して、イベントの発生回数をカウントできます。例えば、サイトでの Real Player と Windows Media Player の使用状況を追跡するとします。各ページには、[!UICONTROL 貼り付けるコード]が含まれており、このコード内に [!UICONTROL s.prop] 変数があります。[!UICONTROL s.prop]1 を使用して、プレイヤーを追跡します。ページ A では、[!UICONTROL s.prop]1 に Real Player を表す値を入力します。

```js
s.prop1="RealPlayer"
```

同様にページ B では、次のように、[!UICONTROL s.prop]1 に Windows Media Player を表す値を入力します。

```js
s.prop1="WindowsMP"
```

>[!NOTE]
>
>Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

訪問者がサイトに来訪して Real Player または Windows Media Player を含むページにアクセスすると、[!DNL Analytics] では、訪問したページに基づいてユーザーをセグメント化できます。[!UICONTROL カスタムトラフィック]レポートに、各ページの訪問数が表示されます。

>[!NOTE]
>
>[!UICONTROL カスタムトラフィック] レポートの名前はカスタマイズできます。例えば、[!UICONTROL カスタムトラフィック]レポートの名前を「プレイヤータイプレポート」に変更できます。

