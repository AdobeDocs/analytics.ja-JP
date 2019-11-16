---
description: デバイス間の訪問者の識別により、レポートに表示されるデータがどのように影響を受けるかについて概要を説明します。
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: デバイス間の訪問者の識別によるデータの影響
topic: Developer and implementation
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# デバイス間の訪問者の識別によるデータの影響

>[!IMPORTANT]
>
>デバイスをまたいで訪問者を識別するこの方法は、非推奨になりました。詳しくは、 [Adobe Experience Cloud Device Co-opのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

デバイス間の訪問者の識別により、レポートに表示されるデータがどのように影響を受けるかについて概要を説明します。

この機能によるデータ収集への影響を理解するために、訪問者プロファイル内の訪問者データフィールドを理解すると役に立ちます。

| データフィールド | 説明 |
|---|---|
| 訪問者 ID cookie | デバイスまたはブラウザーからの最初の訪問時に自動的に生成され、`s_vi` cookie に保存される ID。 |
| 訪問者 ID 変数 | [!UICONTROL  変数を使用して設定されるオプションの]訪問者 ID`s.visitorID`。この値は、ユーザーの認証後に設定されます。複数のデジタルマーケティングチャネル間でユーザーを追跡するために社内で使用している ID と一致する場合があります。 |
| 有効な訪問者 ID | 有効な[!UICONTROL 訪問者 ID] とは、ユーザープロファイルの実際の ID のことです。この値は、[!UICONTROL 訪問者 ID] cookie または [!UICONTROL 訪問者 ID] 変数（提供される場合）に設定されます。 |

