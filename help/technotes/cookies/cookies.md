---
title: Adobe Analytics とブラウザーの cookie
description: トラッキング防止対策が、Adobe Analyticsが設定したサードパーティCookieおよびファーストパーティCookieにどのような影響を与えるかを説明します。
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 7%

---


# Adobe Analytics とブラウザーの cookie

このドキュメントでは、主要ブラウザーのトラッキング防止措置が、Adobe Analyticsが設定するサードパーティCookieおよびファーストパーティCookieに与える影響について説明します。 これには、AppleのIntelligent Tracking Prevention(ITP)プログラムに関する情報と、SameSite属性を使用したサードパーティcookieに対するChromeの制限事項が含まれます。

## ブラウザーでcookieの使用が制限されているのはなぜですか。

### サードパーティCookieの制限

サードパーティコンテキストで使用されるcookieは、広く非推奨となっています。 FirefoxとSafariは、それぞれ2019年と2020年から、デフォルトでサードパーティCookieのブロックを開始しています。 Chromeは、2022年のいつかにサードパーティCookieのサポートを停止する計画を発表しました。 削除すると、サードパーティCookieは事実上使用できなくなります。

また、現在Chromeでは、cookieが「SameSite」属性が「なし」に設定され、セキュリティで保護されているとラベルが付けられている場合、cookieがサードパーティコンテキストで機能するのは、HTTPS経由でのみ使用できます。 詳しくは、「[SameSite cookie属性とは何ですか。また、Analyticsに与える影響は何ですか？](#samesite-effect)」を参照してください。

#### 影響を受けるのは、どのAdobeのサードパーティcookieですか。

訪問者IDサービスは、異なる顧客ドメイン間の訪問者に対して永続的な識別子を提供するために、[`demdex.net`](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) cookieを使用します。 サードパーティcookieがブロックされているブラウザーでは、クロスドメイントラッキングは使用できません。

### ファーストパーティCookieの制限{#limitations-first-party-cookies}

ファーストパーティcookieは、すべての主要ブラウザーで許可されます。 ただし、AppleのIntelligent Trackingプログラム(ITP)を通じてAdobeが設定するファーストパーティCookieの有効期限は制限されています。 これには、MacOSではSafari、iOSおよびiPadOSではすべてのブラウザーが含まれます。

Adobeのファーストパーティcookieは、7日間の有効期限または24時間の有効期限（Appleがトラッカーからの訪問と判断した場合）に制限されます。 7日間の有効期限の場合、ユーザーがサイトを訪問し、その7日以内に再訪した場合、cookieの有効期限はさらに7日延長されます。 ただし、訪問者がサイトを訪問し、8日後に再訪した場合、2回目の訪問では新規ユーザーとして扱われます。

現在、ITPポリシーは、訪問者IDサービスを使用しているか、従来のAnalytics ID(「s_vi」 cookie)を使用しているかに関係なく、Adobeが設定するすべてのファーストパーティcookieに適用されます。 ある時点で、これらのポリシーは、クライアント側に設定されたcookieにのみ適用され、CNAME実装を介してサーバー側に設定されたcookieには適用されません。 ただし、2020年11月には、CNAMEの実装にも適用するようにITPが更新されました。

#### ITPポリシーに対する主な変更の日程

* 2019年2月、[ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/):クライアント側のCookieが7日間の有効期限に制限されていた問題を修正しました。
* 2019年4月、[ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/):クライアント側のcookieは、参照ドメインがaの場合は24時間に制限されていました。また、b)クロスサイトトラッキングに関連する広告クリックおよびb)最終URLにクエリ文字列やフラグメント識別子が含まれていた問題を修正しました。
* 2020年11月、[CNAMEクロークとバウンストラッキングの防御](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/):ITPの制限は、CNAME実装に拡張されました。

ITPポリシーは頻繁に発展しています。 最新のポリシーについては、[Webkit](https://webkit.org/tracking-prevention)での追跡防止を参照してください。

#### 影響を受けるのはどのAdobeのファーストパーティcookieですか。

Adobeが設定するすべてのファーストパーティCookieと関連するJavaScriptライブラリは、ITPポリシーの影響を受けます。

* [`AMCV` Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) 訪問者ID (ECID)サービスライブラリによって設定されるcookie
* CNAMEを使用したファーストパーティデータ収集を使用して設定されたAnalyticsの従来の[`s_vi` cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)
* Analyticsの従来の[`s_fid` cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)。これは、`s_vi`を設定できない場合に使用されるフォールバックcookieです

#### ITPがSafari for Analyticsに与える影響は何ですか。

ITPの制限の影響は、ユーザーの行動に応じて大きく異なります。 影響を受けるのは、ITPの影響を受けたブラウザー(Safari)を使用し、7日間の不在の後に再来訪する訪問者のみです。 訪問者がITPブラウザーを使用していない場合や、7日以内に戻ってくる場合は、影響を受けません。 この制限の影響の程度を理解するには、Analyticsで独自のデータを確認することが重要です。 サイトへの影響を測定する方法のヒントについては、「[Safariの変更が自分のビジネスに影響を与えているかどうかを判断する方法を教えてください。](#measure-itp-effect)」を参照してください。

これらの制限がデータに影響する場合は、次の項目が表示されます。

1. 再訪問者のcookieの有効期限が切れているので、再訪問者としての訪問者カウントが増加しました。 訪問者指標(訪問者あたりの売上高など)に基づく指標も影響を受けます。
2. アトリビューションの変更。 コンバージョンイベントは、同じ訪問者によって前のアクティビティに結び付けられます。 Cookieの有効期限が切れると、今後のイベントは新しい訪問者に関連付けられ、コンバージョンを元の訪問者に結び付けることはできません。

>[!NOTE]
>
>ITPテクノロジーは、現在、モバイルアプリの埋め込みブラウザーには適用されません。

## サードパーティ cookie とファーストパーティ cookie の違いは何ですか？

### サードパーティ Cookie

サードパーティCookieは、ユーザーがアクセスするWebサイトによって作成されるものではありません。

現在、ブラウザーではすべてのサードパーティCookieが同じ扱いになり、それに応じて保存されますが、サードパーティCookieは異なる動作をする場合があります。 お客様のAnalyticsサードパーティcookieの実装では、ブラウザーはAdobe[demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) IDをサードパーティcookieとして保存しますが、クライアントはAdobeに対してのみ呼び出し、未知のドメインや不審なサードパーティドメインは呼び出しません。 このcookieはドメイン間で永続的な識別子を提供し、コンテンツをセキュリティで保護(HTTPS)できます。 詳しくは、[cookie と Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)を参照してください。

Analyticsの導入では、クロスドメイントラッキングや広告の用途（広告の再ターゲティングなど）に、サードパーティcookieが使用されます。 サードパーティCookieを使用すると、所有する異なるドメインの訪問時、または所有しないサイトで広告が表示される場合に、訪問者を識別できます。<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### ファーストパーティ Cookie

ファーストパーティcookieはドメインに固有のもので、顧客のWebサイトによって作成され、ユーザーがWebサイトを訪問したときにクライアントブラウザーに保存されます。 [Safariでは一部のタイプのファーストパーティcookieの有効期限が制限されますが、すべてのブラウザーは通常、ファーストパーティcookieを受け入れます。](#limitations-first-party-cookies)

Analyticsの導入では、ファーストパーティcookieを使用してユーザーがサイトにいるときにユーザーを識別するので、ユーザーアクティビティのすべての分析がサポートされます。 オンサイトのアクティビティを理解するために、サードパーティCookieは必要ありません。

詳しくは、[ファーストパーティ cookie について](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html)を参照してください。

![cookie の比較](/help/technotes/assets/cookies2.png)

## SameSite cookie属性とは何ですか。また、Analytics cookieに与える影響は何ですか。{#samesite-effect}

2020年2月にChrome 80ブラウザーがリリースされ、以降のバージョンのFirefoxおよびEdgeブラウザーが連続すると、SameSite cookie属性は次の3つの異なる値に対する仕様を適用して、クロスサイトリクエストの動作を制御します。

* `None`：この設定によってクロスサイトアクセスが可能になり、cookie をサードパーティコンテキストで渡すことができます。この属性を指定するには、`Secure` を指定する必要があります。また、すべてのブラウザーリクエストは HTTPS に対応しなければなりません。例えば、cookie を設定する場合、「`Set-Cookie: example_session=test12; SameSite=None; Secure`」のように属性の値を組み合わせます。適切にラベル付けされないと、新しいブラウザーではcookieが使用できなくなり、拒否されます。

* `Lax`:セーフ *(読み取り専用、*  `GET`など) HTTPメソッドを使用するトップレベルナビゲーションに対してのみ、同一サイトのCookieを使用してクロスサイトリクエストを送信できます。

* `Strict`：サードパーティ Web サイトのリクエストに対して SameSite cookie が送信されません。サイトが URL バーのサイトと一致する場合にのみ送信されます。

これらのブラウザーバージョンのデフォルトの動作では、指定された `SameSite` 属性を持たない cookie が `SameSite=Lax` と同じように処理されます。

### AnalyticsでのSameSite Cookie属性の管理方法

すべてのAdobeCookieの更新はAdobeサーバーを介して処理され、Adobeエッジサーバーは適切なCookie属性を設定します。 サードパーティCookieはすべて、サーバ側で適切な属性で更新されました。 サイトの JavaScript を更新する必要はありません。

Adobeエッジサーバーによるこのアップグレードは、cookieが使用されたWebサイトの訪問者が自動的に行われます。 ほとんどのAdobe製品では、2020年にChrome 80がリリースされた際に、cookieに適切なフラグが付けられていました。 例外は、サードパーティのデータ収集を使用し、Experience Cloud訪問者IDサービスを使用しないAdobe Analytics実装です。 このタイプの実装の場合、フラグを変更するようカスタマーケアに依頼する必要があります。詳細については、次のセクションの「[複数のドメインに1つのCNAMEを使用する場合は、SameSite値を変更する](#samesite-one-cname)」を参照してください。 フラグが変更されるまでは、新しい訪問者が少し一時的に増加し、それ以外の場合は再訪問者とタグ付けされます。

`SameSite`を`None`に設定した場合、Googleがcookieの処理を誤っていると識別したブラウザーでは、代わりに`SameSite`が設定解除されます。

次の表に、Analytics cookieのSameSite属性の概要を示します。

![cookie 一覧表](/help/technotes/assets/cookies1.png)

### SameSite属性に対するサイトの住所要件を教えてください。

#### すべてのサイトページをHTTPSで提供する

JavaScript設定で、Adobeサービスへのすべての呼び出しにHTTPSを使用していることを確認します。

サイトでExperience Cloud訪問者IDサービスを使用している場合、サードパーティのHTTP呼び出しをHTTPSエンドポイントにリダイレクトするので、待ち時間は長くなりますが、設定を変更する必要はありません。

#### 複数のドメインに1つのCNAMEを使用する場合は、SameSiteの値を変更します{#samesite-one-cname}

>[!NOTE]
>
>次の情報は、Experience Cloud訪問者IDサービスを使用しないサイトにのみ関連しています。

Webサイトと同じドメインに設定されたCNAME実装がある場合、cookieはファーストパーティコンテキストで作成され、変更を行う必要はありません。

ただし、複数のドメインを所有し、すべてのドメインで同じCNAMEをデータ収集に使用する場合、そのCookieは、他のドメインではサードパーティCookieとして扱われます。 Chrome 80以降では、他のドメインでは表示されなくなります。 すべてのブラウザーでこの動作をより似たものにするため、Analyticsでは、このcookieの`SameSite`値を`Lax`に明示的に設定しています。 このcookieをわかりやすいサードパーティコンテキストで使用する場合は、cookieに`SameSite=None`値を設定する必要があります。つまり、常にHTTPSを使用する必要があります。 まだ変更していない場合は、Adobeカスタマーケアに問い合わせて、セキュアなCNAMEのSameSite値を変更してもらいます。

## Safariの変更がビジネスに影響を与えているかどうかを確認する方法を教えてください。{#measure-itp-effect}

Adobeでは、データ収集を変更する前に、お客様が独自の会社内で影響を測定することを推奨します。 Analysis Workspaceを使用して、個々のビジネスに対するITPトラッキング防止の影響を測定できます。

* ITPで管理されるブラウザーからのトラフィックの割合を測定します。

   1. セグメントを作成して、ITPプラットフォームを使用している訪問者の数を確認します。

      ![ITP訪問者のセグメント](/help/technotes/assets/itp-visitor-segment.png)

   2. このセグメントを訪問数に適用すると、ユーザーベースでのSafariの相対的な使用状況がわかります。 これにより、次のようなテーブルを作成できます。

      ![ITP訪問者別の訪問の割合](/help/technotes/assets/visits-vs-safari-visits.png)

* 7日以内に返されないSafari以外のブラウザーを使用して、訪問者の割合を測定します。 7日以内に繰り返しSafari以外の訪問者が再訪する場合は、Safariのトラフィックに大きな影響を与えない可能性があります。

   1. Safari以外のトラフィックに対して、次のようなセグメントを作成します。

      ![7日後に戻る訪問者のセグメント](/help/technotes/assets/visits-after-seven-days.png)

   2. このセグメントを訪問数に適用すると、ユーザーベースでのSafariの相対的な使用状況がわかります。 これにより、次のようなテーブルを作成できます。

      ![7日後に再訪する訪問者の割合](/help/technotes/assets/percent-visits-after-seven-days.png)

### レポート中のデータの調整方法

ITPトラッキングの予防の影響を受けるビジネスの場合は、レポート中にデータを調整するために、以下の対策を検討する必要があります。

* ITPユーザーをフィルターで除外するセグメントを作成します。

   ![ITP以外の訪問者のセグメント](/help/technotes/assets/non-itp-visitor-segment.png)

* 既知の訪問者の水増しに合わせて調整する計算指標を作成します。

   ![訪問者の水増しに合わせて調整する計算指標](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[ブラウザーのCookie制限の影響を軽減するオプション](cookieless.md)
>[Appleの新しいアプリトラッキング透明性フレームワークがAdobe Analyticsに及ぼす影響](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
