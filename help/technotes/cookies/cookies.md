---
title: Adobe Analytics とブラウザーの cookie
description: トラッキング防止対策が、Adobe Analytics によって設定されたサードパーティ cookie およびファーストパーティ cookie にどのように影響するかを説明します。
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: ht
source-wordcount: '1985'
ht-degree: 100%

---

# Adobe Analytics とブラウザーの cookie

このドキュメントでは、主要なブラウザーのトラッキング防止策が Adobe Analytics によって設定されたサードパーティ cookie およびファーストパーティ cookie にどのように影響するかを説明します。Apple の Intelligent Tracking Prevention（ITP）プログラムに関する情報と、SameSite 属性を使用したサードパーティ cookie に対する Chrome の制限について説明します。

## ブラウザーでの cookie の使用制限

>[!NOTE]
>[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja#cda)および [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja#comparing-cja-to-traditional-adobe-analytics) では、利用可能な場合は、ハッシュ化されたログイン ID など、個人 ID を使用して cookie をまたいで関連付けできます。

### サードパーティ cookie の制限

サードパーティのコンテキストで使用される cookie は、広く非推奨（廃止予定）となっています。Firefox と Safari は、それぞれ 2019 年と 2020 年から、デフォルトでサードパーティ cookie のブロックを開始しました。Chrome は、2023 年中にサードパーティ cookie のサポートを停止する計画を発表しました。その場合、サードパーティ cookie を事実上使用できなくなります。

さらに、現在、Chrome では、「SameSite」属性が「なし」に設定され、セキュアとしてラベル付けされている場合（つまり HTTPS 経由でのみ使用できる）にのみ、cookie がサードパーティコンテキストで機能することを許可しています。詳しくは、「[SameSite cookie 属性とは何ですか？また、Analytics にどのような影響を与えますか？](#samesite-effect)」の節を参照してください。

#### 影響を受けるアドビのサードパーティ cookie

訪問者 ID サービスは、「[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=ja)」 cookie を使用して、異なる顧客ドメインをまたいで訪問者の永続的な識別情報を提供します。従来の Analytics ID サービスである「s_vi」 cookie は、カスタム CNAME 収集ドメインを使用しない実装ではサードパーティ cookie として設定されます。

サードパーティ cookie がブロックされているブラウザーでは、クロスドメイントラッキングを使用できません。

### ファーストパーティ cookie の制限 {#limitations-first-party-cookies}

ファーストパーティ cookie は、すべての主要なブラウザーで許可されています。ただし、Apple では、インテリジェントトラッキングプログラム（ITP）を通じて、アドビによって設定されたファーストパーティ cookie の有効期間を制限しています。これは、Safari に加えて、iOS および iPadOS のすべてのブラウザーに影響します。

Adobe のファーストパーティ cookie の有効期限は 7 日間になります。また、Apple によってトラッカーからのクリックスルーだとみなされた場合は、有効期限が 24 時間になります。有効期限が 7 日間の場合、ユーザーがサイトを訪問して 7 日以内に戻った場合、cookie の有効期限はさらに 7 日間延長されます。ただし、サイトを訪問して 8 日後に戻ったユーザーは、2 回目の訪問では新しいユーザーとして扱われます。

現在、ITP ポリシーは、訪問者 ID サービスと従来の Analytics ID（「s_vi」 cookie）のどちらを使用している場合でも、アドビが設定しているすべてのファーストパーティ cookie に適用されます。かつては、これらのポリシーはクライアントサイドで設定された cookie にのみ適用され、CNAME 実装を介してサーバーサイドで設定された cookie には適用されていませんでしたが、2020 年 11 月に、ITP が更新され、CNAME 実装にも適用されるようになりました。

#### ITP ポリシーの大幅な変更のタイムライン {#ITP-timeline}

* 2019 年 2 月（[ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)）：クライアントサイド cookie の有効期限が 7 日間に制限
* 2019 年 4 月（[ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/)）：参照ドメインが（a）クロスサイトトラッキングに関与し、（b）最終 URL にクエリー文字列やフラグメント識別子が含まれていた場合、クライアントサイド cookie は広告のクリックに対して 24 時間に制限
* 2020 年 11 月（[CNAME クローキングとバウンストラッキングの防御](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/)）：ITP　の制限が CNAME 実装に拡張

ITP ポリシーは頻繁に進化しています。最新のポリシーについては、Apple の『[Webkit でのトラッキング防止 ](https://webkit.org/tracking-prevention)』を参照してください。

#### 影響を受けるアドビのファーストパーティ cookie

アドビによって設定されているすべてのファーストパーティ cookie および関連する JavaScript ライブラリは、ITP ポリシーの影響を受けます。

* Adobe Experience Cloud 訪問者 IDID（ECID）サービスライブラリによって設定される[「AMCV」 cookie](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=ja)
* CNAME を使用したファーストパーティデータ収集で設定されている場合の、Analytics 従来の[「s_vi」 cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja)
* Analytics 従来の[「s_fid」 cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja)（「s_vi」を設定できない場合に使用されるフォールバック cookie）

#### Safari の Analytics への ITP の影響

ITP の制限の影響は、ユーザーの行動によって大きく異なる場合があります。ITP の影響を受けたブラウザー（Safari など）を使用し、7 日間の不在の後に再訪問した訪問者のみが影響を受けます。ITP ブラウザーを使用していない場合や、7 日以内に再訪した場合は、影響を受けません。Analytics で独自のデータを確認して、この制限の影響の程度を把握することが重要です。サイトへの影響の測定方法に関するヒントは、「[Safari の変更が自社のビジネスに影響を与えるかどうかを確認する方法](#measure-itp-effect)」を参照してください。

これらの制限がデータに影響を与えている場合、次が当てはまります。

1. 訪問者の cookie の有効期限が切れているので、新しい訪問者としてカウントされる訪問者が増加します。訪問者指標（訪問者あたりの売上高など）に基づく指標も影響を受けます。
2. アトリビューションの変更 -アトリビューションは、コンバージョンイベントと、同じ訪問者の先行するアクティビティとを結び付けることに依存します。Cookie の有効期限が切れると、以降のイベントは新しい訪問者に関連付けられます。新しい訪問者のアクティビティを以前の訪問者のアクティビティに結び付けることはできません。

>[!NOTE]
>
>ITP テクノロジーは現在モバイルアプリに埋め込まれたブラウザーには適用されません。

## サードパーティ cookie とファーストパーティ cookie の違いは何ですか？

### サードパーティ Cookie

サードパーティ cookie は、ユーザーが訪問する Web サイトによって作成されるものではありません。

現在、ブラウザーはすべてのサードパーティ cookie を同じように処理して保存しますが、サードパーティ cookie はそれぞれ異なる方法で動作する場合があります。お客様の Analytics サードパーティ cookie の実装では、ブラウザーは Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=ja) ID をサードパーティ cookie として保存しますが、クライアントは Adobe に対してのみ呼び出しをおこない、不明な、または疑わしいサードパーティドメインは呼び出しません。この cookie はドメイン間で永続的な識別子と（HTTPS による）安全なコンテンツを提供します。詳しくは、[cookie と Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=ja)を参照してください。

Analytics 実装では、サードパーティ cookie がクロスドメイントラッキングや広告の使用例（リターゲティング広告を含む）に使用されます。サードパーティ cookie を使用すると、訪問者が所有する別のドメインにアクセスしたときや所有していないサイトで広告が表示されたときに、訪問者を識別できます。<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### ファーストパーティ ｃookie

ファーストパーティ cookie はドメイン固有で、顧客の Web サイトによって作成され、ユーザーが Web サイトを訪問するとクライアントブラウザーに保存されます。[Safari では一部のタイプのファーストパーティ cookie の有効期限が制限されます](#limitations-first-party-cookies)が、通常、すべてのブラウザーはファーストパーティ cookie を受け入れます。

Analytics 実装では、ファーストパーティ cookie を使用して、サイトを訪問中のユーザーが特定され、その結果、ユーザーアクティビティの分析がすべてサポートされます。オンサイトアクティビティを理解するのにサードパーティ cookie は必要ありません。

詳しくは、[ファーストパーティ cookie について](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja)を参照してください。

![cookie の比較](/help/technotes/assets/cookies2.png)

## SameSite cookie 属性とは何ですか？また、Analytics cookie にどのような影響を与えますか？ {#samesite-effect}

2020 年 2 月の Chrome 80 ブラウザーのリリース（および Firefox と Edge の今後のバージョン）では、 SameSite cookie 属性によって、cookie をサードパーティコンテキストで使用できるかどうかを制御する 3 つの異なる値が指定されます。

* `None`：この設定によってクロスサイトアクセスが可能になり、cookie をサードパーティコンテキストで渡すことができます。この属性を指定するには、`Secure` を指定する必要があります。また、すべてのブラウザーリクエストは HTTPS に対応しなければなりません。例えば、cookie を設定する場合、「`Set-Cookie: example_session=test12; SameSite=None; Secure`」のように属性の値を組み合わせます。ラベル付けが適切でない場合、新しいブラウザーで cookie を使用できなくなり、拒否されます。

* `Lax`：*安全な*（`GET` などの読み取り専用の）HTTP メソッドを使用するトップレベルナビゲーションに対してのみ、SameSite cookie を使用してクロスサイトリクエストを送信できます。

* `Strict`：サードパーティ Web サイトのリクエストに対して SameSite cookie が送信されません。サイトが URL バーのサイトと一致する場合にのみ送信されます。

これらのブラウザーバージョンのデフォルトの動作では、指定された `SameSite` 属性を持たない cookie が `SameSite=Lax` と同じように処理されます。

### Analytics が SameSite cookie 属性を管理する方法

訪問者 ID サービスを使用している顧客の場合、cookie のプロパティ `SameSite=None` と `secure` はデフォルトで設定されているので、これらの cookie でサードパーティの使用例をサポートできます。

Analytics の従来の識別子（「s_vi」および「s_fid」 cookie）を使用している顧客の場合、cookie は、標準の収集ドメイン（adobedc.net、2o7.net および omtrdc.net）を持つサードパーティの使用例も有効にするように設定されています。CNAME 実装を使用している顧客の場合、Analytics は `SameSite=Lax` を設定しています。

>[!NOTE]
>
>ただし、複数のドメインを所有し、すべてのドメインで同じ CNAME をデータ収集に使用する場合、他のドメインではサードパーティ cookie として扱われます。従来の Analytics 識別子を使用している場合は、サイト全体でこれらの cookie を共有できるように、設定を `SameSite=None` に更新する必要がある場合があります。詳しくは、次の節の「[複数のドメインに 1 つの CNAME を使用する場合の SameSite 値の変更](#samesite-one-cname)」を参照してください。

`SameSite` が `None` に設定されており、ブラウザーによる cookie の処理が誤っていると Google によって認識された場合、`SameSite` は未設定のままになります。

次の表に、Analytics cookie の SameSite 属性の概要を示します。

![cookie 一覧表](/help/technotes/assets/cookies1.png)

### SameSite 属性に対する要件にサイトで対処する方法

#### すべてのサイトページを HTTPS で提供する

JavaScript 設定で、アドビのサービスへのすべての呼び出しに HTTPS が使用されていることを確認します。

サイトで Experience Cloud 訪問者 ID サービスを使用している場合、サービスはサードパーティの HTTP 呼び出しをその HTTPS エンドポイントにリダイレクトします。待ち時間が長くなる可能性がありますが、設定を変更する必要がなくなります。

#### 複数のドメインに 1 つの CNAME を使用する場合の SameSite 値の変更 {#samesite-one-cname}

>[!NOTE]
>
>次の情報は、訪問者 ID サービスを使用しない Experience Cloud にのみ関係します。

Web サイトと同じドメインに設定された CNAME 実装がある場合、Cookie はファーストパーティコンテキストで作成されているので、変更をおこなう必要はありません。

ただし、複数のドメインを所有し、すべてのドメインで同じ CNAME をデータ収集に使用する場合、他のドメインではサードパーティ cookie として扱われます。Chrome 80 以降では、他のドメインでは表示されなくなります。Analytics では、すべてのブラウザーにおいて動作を統一するために、この cookie の `SameSite` 値を `Lax` に明示的に設定しています。この cookie を明確なサードパーティコンテキストで使用する場合は、cookie に `SameSite=None` 値を設定し、常に HTTPS を使用する必要があります。セキュアな CNAME の SameSite 値を変更していない場合は、アドビのカスタマーケアにお問い合わせください。

## Safari の変更が自社のビジネスに影響を与えるかどうかを確認する方法  {#measure-itp-effect}

アドビでは、データ収集を変更する前に、自社内の影響を測定することをお勧めします。Analysis Workspace を使用して、ITP トラッキング防止が個々のビジネスに与える影響を測定できます。

* ITP が管理されるブラウザーからのトラフィックの割合を測定します。

   1. セグメントを作成して、ITP プラットフォームを使用している訪問者の数を確認します。

      >[!NOTE]
      >
      >ITP の影響を受けるブラウザーは、CNAME 実装を使用しているかどうかによって異なります。詳しくは、「[ITP ポリシーの大幅な変更のタイムライン](#ITP-timeline)」を参照してください。

      ![ITP 訪問者のセグメント](/help/technotes/assets/itp-visitor-segment.png)

   2. 訪問回数にセグメントを適用して、ユーザーベースでの Safari の相対的な使用状況を把握します。次のようなテーブルを作成できます。

      ![ITP 訪問者による訪問の割合](/help/technotes/assets/visits-vs-safari-visits.png)

* 7 日以内に戻らない Safari 以外のブラウザーを使用している訪問者の割合を測定します。Safari 以外の訪問者が 7 日以内に繰り返し再訪した場合、Safari トラフィックは大きな影響を受けない可能性があります。

   1. Safari 以外のトラフィックに対して、次のようなセグメントを作成します。

      ![7 日後に再訪した訪問者のセグメント](/help/technotes/assets/visits-after-seven-days.png)

   2. 訪問回数にセグメントを適用して、ユーザーベースでの Safari の相対的な使用状況を把握します。次のようなテーブルを作成できます。

      ![7 日後に再訪する訪問者の割合](/help/technotes/assets/percent-visits-after-seven-days.png)

### レポート中にデータを調整する方法

ITP トラッキング防止の影響を受けているビジネスは、レポート中にデータを調整するために、次の措置を検討する必要があります。

* ITP ユーザーを除外するセグメントを作成します。

   ![ITP 以外の訪問者のセグメント](/help/technotes/assets/non-itp-visitor-segment.png)

* 既知の訪問者の水増しに合わせて調整する計算指標を作成します。

   ![訪問者の水増しに合わせて調整する計算指標](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[ブラウザーの cookie 制限の影響を軽減するオプション](cookieless.md)
>[Apple の新しい App Tracking Transparency Framework が Adobe Analytics に及ぼす影響](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833?profile.language=ja)
