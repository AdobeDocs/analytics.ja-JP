---
title: account
description: アカウント変数を使用して、データの送信先のレポートスイートを決定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# account

> [!IMPORTANT] この変数は廃止されます。 導入でレポー [`s.sa()`](../functions/sa-method.md) トスイートの宛先を変更する必要がある場合は、この関数を使用します。

以前のバージョンのAdobe Analyticsでは、変数は `account` データの送信先のレポートスイートを決定していました。 Adobe Analyticsにデータを送信するには、レポートスイートIDが必要です。

* Adobe Experience Platform Launchを使用する場合、Adobe Analytics拡張の設定時に、レポートスイー [!UICONTROL Library Management] トはアコーディオンの下に配置されます。
* この関数を使用してAnalytics [`s_gi()`](../functions/s-gi.md) 追跡オブジェクトをインスタンス化する場合、レポートスイートIDは、関数内の必須の引数として既に存在します。
