---
title: Adobe Analyticsへのログインのトラブルシューティング
description: Adobe Analyticsにログインできない場合に実行する手順です。
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 5%

---


# Adobe Analyticsへのログインのトラブルシューティング

Adobe AnalyticsはAdobe IDを使用してExperience Cloudの認証を行います。

Analyticsに定期的にアクセスし、ランダムな開始でログインの問題が発生した場合、ブラウザーのCookieとキャッシュを消去すると、ほとんどの場合この問題が解決されます。

## Access experience.adobe.com

experience.adobe.com [に移動します](https://experience.adobe.com)。

このサイトにアクセスできない場合：

* お使いの組織では、ファイアウォールを通じてこのドメインを許可していない可能性があります。 組織のITチームと協力して許可します。 ITチームに役立つ情報については、 [Adobe Experience Cloudで使用されるIPおよびドメイン](https://helpx.adobe.com/jp/analytics/kb/adobe-ip-addresses.html) を参照してください。
* status.adobe.com [](https://status.adobe.com) を確認して、使用できる問題がないことを確認します。

## Adobe IDを使用して認証する

「**[!UICONTROL Adobe ID を使用してサインイン]**」をクリックします。

サインインできない場合：

* 重複は、電子メールアドレスが正しく入力されているかどうかを確認します。
* 「 **[!UICONTROL パスワードをリセット]** 」をクリックし、画面の指示に従ってAdobe IDをリセットします。

## 認証後にAnalyticsにアクセスできません

右上の9-gridアイコンをクリックし、「Analytics」をクリックします。

このオプションがない場合、または灰色表示になっている場合は、組織内の製品管理者に問い合わせて、Analyticsへのアクセスに適切な権限があることを確認してください。

## その他のエッジケースログインの問題

上記の手順がいずれも機能しない場合は、ログインの問題の幅を判断します。

* この問題は、異なるブラウザーを使用する場合に発生しますか。それとも、すべてのブラウザーで発生しますか。
* この問題は、ネットワーク上の別のマシンで発生しますか。それとも、複数のマシンで発生しますか。
* モバイルデータ接続、ライブラリ、ホームネットワークなど、別のネットワークを使用してログインしてみてください。 この問題はネットワーク間で発生しているか。

この問題がネットワーク内で切り離されている場合は、組織のITチームと協力して問題を解決します。 1つのネットワークに限定されない場合は、Adobeカスタマーケアにお問い合わせください。
