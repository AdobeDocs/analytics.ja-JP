---
title: account
description: Account 変数を使用して、データの送信先のレポートスイートを決定します。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '110'
ht-degree: 100%

---

# account

>[!IMPORTANT]
>
> この変数は廃止されています。実装でレポートスイートの宛先を変更する必要がある場合は、[`s.sa()`](../functions/sa-method.md) 関数を使用します。

以前のバージョンの Adobe Analytics では、`account` 変数はデータの送信先のレポートスイートを決定しました。Adobe Analytics にデータを送信するには、レポートスイート ID が必要です。

* Adobe Experience Platform のタグを使用する場合、Adobe Analytics 拡張機能の設定時に、レポートスイートは「[!UICONTROL ライブラリ管理]」アコーディオンの下に配置されます。
* [`s_gi()`](../functions/s-gi.md) 関数を使用して Analytics トラッキングオブジェクトをインスタンス化する場合、その関数内には必須の引数としてレポートスイート ID が既に存在します。
