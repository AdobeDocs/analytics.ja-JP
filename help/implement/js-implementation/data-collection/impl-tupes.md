---
description: この情報は、レポートと導入の両方に精通している上級ユーザー向けです。導入を変更した場合の影響を把握していない場合は、導入を変更しないでください。導入を変更する必要がある場合は、社内のアカウントマネージャーにお問い合わせください。
keywords: Analytics Implementation
title: 異なる実装タイプでのトラッキング
topic: Developer and implementation
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 異なる実装タイプでのトラッキング

この情報は、レポートと導入の両方に精通している上級ユーザー向けです。導入を変更した場合の影響を把握していない場合は、導入を変更しないでください。導入を変更する必要がある場合は、社内のアカウントマネージャーにお問い合わせください。

複数の導入タイプ（JavaScript やハードコードされたイメージリクエストなど）を使用する場合は、次の変数が指定され、互いに一致していることを確認します。

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`*（SSL を使用する場合）

これらの変数が導入間で一致しない場合は、ユーザーが個別の訪問者として追跡される可能性があります。
