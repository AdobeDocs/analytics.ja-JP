---
title: account
description: （廃止）データの送信先のレポートスイートを決定します。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
> この変数は廃止されています。実装でレポートスイートの宛先を変更する必要がある場合は、[`s.sa()`](../functions/sa-method.md) 関数を使用します。

以前のバージョンの Adobe Analytics では、`account` 変数はデータの送信先のレポートスイートを決定しました。Adobe Analytics にデータを送信するには、レポートスイート ID が必要です。

* Web SDK を使用する場合、レポートスイートは、Web SDK がデータを送信するデータストリーム内のAdobe Analytics サービス設定にあります。
* Adobe Analytics拡張機能を使用する場合、Adobe Analytics拡張機能の設定時に、レポートスイートは [!UICONTROL  ライブラリ管理 ] アコーディオンの下に配置されます。
* [`s_gi()`](../functions/s-gi.md) 関数を使用して Analytics トラッキングオブジェクトをインスタンス化する場合、その関数内には必須の引数としてレポートスイート ID が既に存在します。
