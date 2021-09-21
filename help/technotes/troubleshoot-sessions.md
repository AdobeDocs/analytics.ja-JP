---
title: Adobe Analytics でのセッションのトラブルシューティング
description: Adobe Analytics からログアウトする際の問題を解決する方法について説明します。
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: ht
source-wordcount: '347'
ht-degree: 100%

---

# Adobe Analytics でのセッションのトラブルシューティング

このページでは、セッションのトラブルシューティング（正常にログインできるが、ログイン中に問題が発生する場合）について説明します。Adobe Analytics へのログインで問題が発生する場合は、[Adobe Analytics へのログインのトラブルシューティング](troubleshoot-login.md)を参照してください。

セッションに関する問題の多くは、カスタマイズされた企業ネットワークから発生しています。Adobe Analytics にログインできるものの、ログイン中に問題が発生する場合、この記事が原因の特定に役立ちます。

## 問題が自社のネットワークに起因するものかどうかを特定する

多くの組織では、プロキシサーバーやファイアウォールなど、セキュリティを強化するためのネットワーク機能を導入しています。こうしたネットワークへのカスタマイズが、Adobe Analytics でアクティブなセッションを保持する機能の妨げになる場合があります。

接続している企業ネットワークが Adobe Analytics の使用に問題を引き起こしているかどうかを判断するには、企業ネットワークに接続していないデバイスで Experience Cloud のログイン認証情報を使用します。デバイスの例としては、ホームネットワークやモバイルデバイスのデータプランなどがあります。ログアウトせずにページ間を正常に移動できる場合は、企業ネットワークが Adobe Analytics からのログアウトを引き起こす原因である可能性があります。

## プロキシによる問題

アドビにリクエストを送信する際には、認証ヘッダーが使用されます。Edge Secure Web Gateway（旧称 Bluecoat）などの一部のプロキシは、Adobe Analytics が使用する重要な認証ヘッダー情報を取り除きます。認証ヘッダーが表示されない場合、セッションの有効期限が切れます。

この問題を解決するには、貴社の IT 部門に依頼して、貴社のプロキシを通じて認証ヘッダーを許可することをお勧めします。

>[!NOTE]
>
> Analytics コミュニティのメンバーは、次のリンクが役に立つと判断しましたが、これらのリンクはアドビが所有しているものではありません。コンテンツを表示する際は、この点に留意してください。

 のプロキシと認証ヘッダーに関する情報は、次を参照してください。

* [ProxySG または ASG アプライアンスでのプロキシチェーンデプロイメントにおけるアップストリームプロキシ認証を設定する](https://knowledge.broadcom.com/external/article/169255/configure-upstream-proxy-authentication.html)
* [ProxySG アプライアンスの背後にあるサーバーにユーザーの資格情報を転送する方法](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
