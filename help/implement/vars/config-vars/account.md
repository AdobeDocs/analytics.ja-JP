---
title: account
description: Account 変数を使用して、データの送信先のレポートスイートを決定します。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 47%

---

# アカウント

>[!IMPORTANT]
>
> この変数は廃止されています。実装でレポートスイートの宛先を変更する必要がある場合は、[`s.sa()`](../functions/sa-method.md) 関数を使用します。

以前のバージョンの Adobe Analytics では、`account` 変数はデータの送信先のレポートスイートを決定しました。Adobe Analytics にデータを送信するには、レポートスイート ID が必要です。

* Web SDK を使用する場合、Web SDK がデータを送信する Datastream 内のAdobe Analyticsサービス設定にレポートスイートが含まれます。
* Adobe Analytics拡張機能を使用する場合、レポートスイートは [!UICONTROL ライブラリ管理] アコーディオンを使用してAdobe Analytics拡張機能を設定する際に使用します。
* 次の [`s_gi()`](../functions/s-gi.md) 関数を使用して Analytics トラッキングオブジェクトをインスタンス化する場合、関数内には必須の引数としてレポートスイート ID が既に存在します。
