---
description: マーケティングチャネルで訪問者のエンゲージメント期間を指定する方法について説明します。
solution: Analytics
subtopic: Marketing channels
title: 訪問者のエンゲージメント期間
topic: Reports and analytics
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 訪問者のエンゲージメント期間

マーケティングチャネルで訪問者のエンゲージメント期間を指定する方法について説明します。

訪問者のエンゲージメント期間とは、訪問者のサイトにおけるアクティビティをどれだけの期間、ファーストタッチチャネルに関連付けるかということです。

例えば、訪問者は有料検索キャンペーンをクリックスルーして、製品を買い物かごに追加しますが、コンバージョンイベントに到達する前にセッションを終えることがよくあります。この訪問者が後で再来訪して購入した場合、前回のアクティビティと今回のアクティビティのどちらが 1 回のエンゲージメントとしてカウントされるかを指定できます。デフォルトの期間設定は 30 日間です。

| フィールド | 定義 |
|--- |--- |
| 日間アクセスが無い場合 | 訪問者のファーストタッチエンゲージメント期間の期限が切れるまでの日数。デフォルト値は 30 です。 |
| なし |  訪問者のエンゲージメント期間の期限は切れません。 |
| チャネルリセット | すべての訪問者のエンゲージメント期間を今すぐ期限切れにします。すべてのマーケティングチャネルデータをリセットする必要がある場合は、すべての訪問者のエンゲージメント期間を期限切れにすることができます。以前に処理ルールが正しく設定されていなかった場合には、データをリセットする必要がある場合があります。すべてのファーストタッチチャネルおよびラストタッチチャネルの値はすぐに期限切れになり、訪問者が再訪問したときにリセットされます。 |

## 訪問者のエンゲージメント期間の指定 {#specify-visitor-expire}

訪問者のエンゲージメント期間を指定します。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. In the [!UICONTROL Report Suite Manager], click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Expiration]**.

   ![](assets/mchannel_expiration.png)

1. 訪問者のエンゲージメント期間のフィールドを設定します。
1. Click **[!UICONTROL Save.]**
