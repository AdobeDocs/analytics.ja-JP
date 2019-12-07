---
description: 'null'
keywords: Analytics Implementation;link reference;redir
title: モバイルプロトコルでのカスタムリンク測定
topic: Developer and implementation
uuid: eb82de26-da2e-41c2-8924-59b6b5ccef28
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# モバイルプロトコルでのカスタムリンク測定

多くのモバイルデバイスユーザーは、ポッドキャストや着信音などのファイルをデバイスにダウンロードします。多くのモバイルデバイスは JavaScript をサポートしないので、リダイレクトを利用してリンク測定を導入する必要があります。リダイレクトを使用するには、html の href リンクを変更して、REDIR 要素を追加します。カスタムリンクの一般的な形式は以下のようになります。

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

リンク参照を作成するときには、次の点に注意してください。

* URL 値は URL エンコードされている必要があります。
* pageName または page URL (g) パラメーターを設定する必要があります。
* 動的変数で URL パラメーターを読み取ることができますが、設定することはできません。
* cookie が設定されていない場合、アドビのサーバーでは通常の cookie ハンドシェイクが実行されます。
* リンクをトラッキングするには、pe、pev1、pev2 の各パラメーターを含める必要があります。

カスタムリンク測定 URL は、以下のようになります。

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

詳しくは、[離脱リンクトラッキングのリダイレクトに関するホワイトペーパー](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/)を参照してください。
