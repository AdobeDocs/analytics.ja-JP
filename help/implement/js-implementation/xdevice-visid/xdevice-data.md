---
description: デバイス間の訪問者の識別により、レポートに表示されるデータがどのように影響を受けるかについて概要を説明します。
keywords: Analytics の導入
seo-description: デバイス間の訪問者の識別により、レポートに表示されるデータがどのように影響を受けるかについて概要を説明します。
seo-title: デバイス間の訪問者の識別によるデータの影響
solution: Analytics
subtopic: 訪問者数
title: デバイス間の訪問者の識別によるデータの影響
topic: 開発者と導入
uuid: 1db4d149- cd50-4b41- a850-988901f25051
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# デバイス間の訪問者の識別によるデータの影響

>[!IMPORTANT]
>
>デバイス間で訪問者を識別する方法は推奨されなくなりました。[Adobe Experience Cloud Device Co- opのドキュメント](https://marketing.adobe.com/resources/help/en_US/mcdc/)を参照してください。

デバイス間の訪問者の識別により、レポートに表示されるデータがどのように影響を受けるかについて概要を説明します。

この機能によるデータ収集への影響を理解するために、訪問者プロファイル内の訪問者データフィールドを理解すると役に立ちます。

| データフィールド | 説明 |
|---|---|
| 訪問者 ID cookie | デバイスまたはブラウザーからの最初の訪問時に自動的に生成され、`s_vi` cookie に保存される ID。 |
| 訪問者 ID 変数 | [!UICONTROL  変数を使用して設定されるオプションの]訪問者 ID`s.visitorID`。この値は、ユーザーの認証後に設定されます。複数のデジタルマーケティングチャネル間でユーザーを追跡するために社内で使用している ID と一致する場合があります。 |
| 有効な訪問者 ID | 有効な[!UICONTROL 訪問者 ID] とは、ユーザープロファイルの実際の ID のことです。この値は、[!UICONTROL 訪問者 ID] cookie または [!UICONTROL 訪問者 ID] 変数（提供される場合）に設定されます。 |

