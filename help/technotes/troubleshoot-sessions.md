---
title: Adobe Analytics でのセッションのトラブルシューティング
description: Adobe Analytics からログアウトする際の問題を解決する方法について説明します。
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
TQID: https://experienceleague.adobe.com/b8dTBhP3a6FZSmABKtQKTp9XkmYIjfS5--Vbzl6xRGE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 80%

---

# Adobe Analytics でのセッションのトラブルシューティング

このページでは、セッションのトラブルシューティング（正常にログインできるが、ログイン中に問題が発生する場合）について説明します。 Adobe Analytics へのログインで問題が発生する場合は、[Adobe Analytics へのログインのトラブルシューティング](troubleshoot-login.md)を参照してください。

セッションに関する問題の多くは、カスタマイズされた企業ネットワークから発生しています。 Adobe Analytics にログインできるものの、ログイン中に問題が発生する場合、この記事が原因の特定に役立ちます。

## 問題が自社のネットワークに起因するものかどうかを特定する {#network}

多くの組織では、プロキシサーバーやファイアウォールなど、セキュリティを強化するためのネットワーク機能を導入しています。 こうしたネットワークへのカスタマイズが、Adobe Analytics でアクティブなセッションを保持する機能の妨げになる場合があります。

接続している会社のネットワークでAdobe Analyticsの使用に関する問題が発生しているかどうかを判断するには、会社のネットワーク外のデバイスでCX Enterpriseのログイン資格情報を使用します。 デバイスの例としては、ホームネットワークやモバイルデバイスのデータプランなどがあります。 ログアウトせずにページ間を正常に移動できる場合は、企業ネットワークが Adobe Analytics からのログアウトを引き起こす原因である可能性があります。

## プロキシによる問題 {#proxy}

アドビにリクエストを送信する際には、認証ヘッダーが使用されます。 Edge Secure Web Gateway（旧称 Bluecoat）などの一部のプロキシは、Adobe Analytics が使用する重要な認証ヘッダー情報を取り除きます。 認証ヘッダーが表示されない場合、セッションの有効期限が切れます。

この問題を解決するには、貴社の IT 部門に依頼して、貴社のプロキシを通じて認証ヘッダーを許可することをお勧めします。

>[!NOTE]
>
>Analytics コミュニティのメンバーは、次のリンクが役に立つと判断しましたが、これらのリンクはアドビが所有しているものではありません。 コンテンツを表示する際は、この点に留意してください。

のプロキシと認証ヘッダーに関する情報は、次を参照してください。

* [ProxySGまたはASG アプライアンス上のプロキシチェーンのデプロイメントでのアップストリームプロキシ認証の設定](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [ProxySG アプライアンスの背後にあるサーバーにユーザー資格情報を転送する方法](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
