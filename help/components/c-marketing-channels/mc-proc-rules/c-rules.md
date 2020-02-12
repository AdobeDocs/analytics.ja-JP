---
title: マーケティングチャネルの処理ルール
description: マーケティングチャネルの処理ルールは、訪問者のヒットがチャネルに割り当てられた条件を満たすかどうかを判断するために使用します。このルールは、サイトでの訪問者によるすべてのヒットを処理します。チャネルの条件をルールが満たしていない場合やルールが正しく設定されていない場合、ヒットには「チャネルが識別されませんでした」が割り当てられます。
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# マーケティングチャネルの処理ルール

マーケティングチャネルの処理ルールは、訪問者のヒットがチャネルに割り当てられた条件を満たすかどうかを判断するために使用します。このルールは、サイトでの訪問者によるすべてのヒットを処理します。チャネルの条件をルールが満たしていない場合やルールが正しく設定されていない場合、ヒットには「チャネルが識別されませんでした」が割り当てられます。

ルール作成時の重要なガイドラインは次のとおりです。

* ルールは処理する順序に並べること。
* リストの最後に包括的ルール（「その他」など）を追加すること。このルールは、内部トラフィックではなく外部トラフィックを識別します。

   [チャネルが識別されませんでした](/help/components/c-marketing-channels/mc-faq/c-faq.md#no-channel-identified)を参照してください。

> [!NOTE]これらのルールはマーケティングチャネル以外のレポートには影響しませんが、マーケティングチャネルのデータ収集には影響します。これらのルールを使用して収集されたデータは完全に永久的なもので、データの収集後に変更されたルールを過去のデータにさかのぼって適用させることはできません。It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

## 前提条件

* 「マーケティングチャネル — はじめに [」の概念情報を確認します](/help/components/c-marketing-channels/getting-started/c-getting-started-mchannel.md)。
* ルールを割り当てるためにチャネルを 1 つ以上作成してください。See [Add marketing channels.](/help/components/c-marketing-channels/mark-channel-mgr/c-channels.md)
