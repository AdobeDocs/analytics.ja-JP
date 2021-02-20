---
title: 異なる実装タイプでのトラッキング
description: 異なる実装タイプを使用し、訪問者をシームレスに追跡します。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 100%

---


# 異なる実装タイプでのトラッキング

この情報は、レポートと導入の両方に精通している上級ユーザー向けです。導入を変更した場合の影響を把握していない場合は、導入を変更しないでください。導入を変更する必要がある場合は、社内のアカウントマネージャーにお問い合わせください。

複数の導入タイプ（JavaScript やハードコードされたイメージリクエストなど）を使用する場合は、次の変数が指定され、互いに一致していることを確認します。

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`*（SSL を使用する場合）

これらの変数が導入間で一致しない場合は、ユーザーが個別の訪問者として追跡される可能性があります。
