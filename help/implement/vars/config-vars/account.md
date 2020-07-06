---
title: account
description: Account 変数を使用して、データの送信先のレポートスイートを決定します。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---


# account

>[!IMPORTANT]
>
> この変数は廃止されています。実装でレポートスイートの宛先を変更する必要がある場合は、[`s.sa()`](../functions/sa-method.md) 関数を使用します。

以前のバージョンの Adobe Analytics では、`account` 変数はデータの送信先のレポートスイートを決定しました。Adobe Analytics にデータを送信するには、レポートスイート ID が必要です。

* Adobe Experience Platform Launch を使用する場合、Adobe Analytics 拡張機能の設定時に、レポートスイートは「[!UICONTROL ライブラリ管理]」アコーディオンの下に配置されます。
* [`s_gi()`](../functions/s-gi.md) 関数を使用して Analytics トラッキングオブジェクトをインスタンス化する場合、その関数内には必須の引数としてレポートスイート ID が既に存在します。
