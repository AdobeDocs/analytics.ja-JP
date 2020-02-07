---
title: account
description: アカウント変数を使用して、データの送信先のレポートスイートを決定します。
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# account

> [!IMPORTANT] この変数は廃止されます。 導入でレポー [`s.sa()`](../functions/sa-method.md) トスイートの宛先を変更する必要がある場合は、この関数を使用します。

以前のバージョンのAdobe Analyticsでは、変数は `account` データの送信先のレポートスイートを決定しました。 Adobe Analyticsにデータを送信するには、レポートスイートIDが必要です。

* Adobe Experience Platform Launchを使用する場合、Adobe Analytics拡張の設定時に、レポートスイ [!UICONTROL ートはライブラリ管理] アコーディオンの下に配置されます。
* この関数を使用してAnalytics `s_gi()` トラッキングオブジェクトをインスタンス化する場合、その関数内には必須の引数としてレポートスイートIDが既に存在します。
