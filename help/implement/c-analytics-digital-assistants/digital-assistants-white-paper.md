---
description: 'null'
title: デジタルアシスタント向け Analytics
uuid: c61e6a1a-ec08-4936-9053-5f57223f57ff
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# デジタルアシスタント用のAnalyticsの実装

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

最近のクラウドコンピューティング、機械学習、自然言語処理の進化に伴い、デジタルアシスタントは日常生活の一部となっています。 消費者は自分のデバイスと話し始め、人間のような方法で理解し、対応することを期待している。 こうしたプラットフォームが普及したことで、ブランドは、これと同様の生身の人間のような応対でサービスを消費者に提示できるようになりました。例えば消費者は、次のような質問を投げかけることができます。

* 「Alexa、車のオイル交換が必要な時期を調べて」
* 「Cortana、当座預金口座の残高は？」
* 「Siri、昨夜のディナー代として、ジョンにバンキングアプリから 20 ドル送金して」

このページでは、Adobe Analyticsを使用してこれらのタイプのエクスペリエンスを測定および最適化する方法の概要を説明します。

## デジタルエクスペリエンスアーキテクチャの概要

![](assets/Digital-Assitants.png)

現代のデジタルアシスタントのほとんどでは、大まかなアーキテクチャは同様です。

1. **デバイス：**&#x200B;マイク搭載のデバイス（Amazon Echo や携帯電話）によって、ユーザーが質問を投げかけることができます。
1. **デジタルアシスタント：**&#x200B;そのデバイスが、デジタルアシスタントの基盤のサービスと通信します。音声が機械で認識できる目的に変換され、要求の詳細が解析されます。ユーザーの目的が認識されたら、デジタルアシスタントがその目的と要求の詳細をアプリに渡し、アプリがその要求を処理します。
1. **「アプリ」：**&#x200B;携帯電話のアプリまたは音声アプリです。このアプリが要求に対処し、デジタルアシスタントに返答してから、デジタルアシスタントがユーザーに答えを伝えます。

## Analytics を導入する場所

Analytics を導入する場所として特に効果的なのはアプリです。アプリはデジタルアシスタントから意図と詳細を受け取り、アプリが応答方法を決定します。

リクエストの実行中に、Adobe Analyticsにデータを送信する際に役立つことがある回数は2回です。

1. リクエストがアプリに送信されたとき。
1. アプリから応答が送られたとき。

今後の最適化のために、顧客の状況についての記録のみが必要な場合は、応答が返された後に Adobe Analytics に要求を送信します。リクエストの内容とシステムの応答方法に関する完全なコンテキストが得られます。

## 新規インストール

一部のデジタルアシスタントでは、特に認証に関わる場合に、誰かがスキルをインストールすると通知を受け取ります。 コンテキストデータ変数を設定してInstallイベントを送信することをお勧めしま `a.InstallEvent=1`す。 この機能は、一部のデジタルアシスタントでは利用できませんが、保持期間を調べる際に役立ちます。 次のコードのサンプルを使用すると、Installイベント、Install DateおよびAppIDの値をコンテキストデータ変数に送信できます。

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## 複数のアシスタントまたは複数のアプリ

組織が複数のプラットフォーム用のアプリを必要としている可能性があります。 各要求にアプリ ID を含めることをお勧めします。This variable can be set in the `a.AppID` context data variable. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2:

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## ユーザー/訪問者の識別

Adobe Analyticsは、 [Adobe Experience Cloud Identity Serviceを使用して](https://docs.adobe.com/content/help/en/id-service/using/home.html) 、同じ人物と時間の経過に応じてインタラクションを結び付けます。 ほとんどのデジタルアシスタントは、様々 `userID` なユーザーのアクティビティを保持するために使用できるアクティビティを返します。 ほとんどの場合、この値を一意の識別子として渡すことができます。 一部のプラットフォームは、許可された100文字を超える識別子を返します。 このような場合、固有の識別子を固定長値にハッシュするには、標準のハッシュアルゴリズム（MD5やSha1など）を使用することをお勧めします。

様々なデバイス（例えば、Webアシスタントとデジタルアシスタント）でECIDをマッピングする場合、IDサービスを使用すると最も大きな価値が得られます。 アプリがモバイルアプリの場合は、Experience Platform SDKをそのまま使用し、メソッドを使用してユーザーIDを送信し `setCustomerID` ます。 However, if your app is a service, use the user ID provided by the service as the ECID, as well as setting it in `setCustomerID`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## セッション数

デジタルアシスタントは会話型なので、多くの場合はセッションの概念が採り入れられています。次に例を示します。

**消費者：**「オーケー Google、タクシーを呼んで」

**Google：**:「わかりました。何時に来てもらいますか？」

**消費者：** 「午後 8 時半」

**Google：**「了解しました。午後 8 時半までに運転手が到着します」

セッションは、状況を把握し、デジタルアシスタントをより自然にするために、より詳細な情報を収集するのに役立ちます。 会話にAnalyticsを実装する場合、新しいセッションが開始されるときに行うことができることが2つあります。

1. **Audience Manager にアクセスする：**&#x200B;返答をカスタマイズするために、ユーザーが属する適切なセグメントを取得します（このユーザーは現在、マルチチャネルの割り引きの利用条件を満たしているなど）。
2. **新規セッションまたは開始イベントを送信する：**&#x200B;最初の応答を Analytics に送信する際に、開始イベントを含めます。一般的には、`a.LaunchEvent=1` のコンテキストデータを設定することで、このイベントを送信できます。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## 目的

デジタルアシスタントには、目的を検知してから、対処方法を導き出すためにその目的を「アプリ」に渡すためのアルゴリズムがあります。こうした目的は、要求を簡潔に表現するもので、

例えばユーザーが「Siri、昨夜のディナー代として、ジョンにバンキングアプリから 20 ドル送金して」と言った場合は、その目的は   *sendMoney*.

これらの各リクエストをeVarとして送信することで、会話アプリの各インテントに対してパスレポートを実行できます。 アプリで、意図せずにリクエストを処理できることを確認します。 変数を省略するのではなく、インテントコンテキストデータ変数に「インテントが指定されていません」を渡すことをお勧めします。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

 または

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## パラメーター／スロット／エンティティ

デジタルアシスタントは、意図に加えて、多くの場合、意図の詳細を提供するキーと値のペアを持ちます。 これらは、スロット、エンティティ、またはパラメータと呼ばれます。 例えば、「Siri, Send John $20 for dinner last night from my banking app」には次のパラメーターが含まれます。

* 誰 = ジョン
* 金額 = 20
* 理由 = ディナー

通常、アプリには有限数の値が含まれます。 Analyticsでこれらの値を追跡するには、コンテキストデータ変数に値を送信し、各パラメーターをeVarにマッピングします。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## エラー状態

デジタルアシスタントでは、処理方法がわからない入力をアプリに提供する場合があります。 例えば、「Siri, Send John 20 bags of diner for my banking app」のように記述します。

この状況が発生した場合は、アプリに明確な説明を求めるように指示してください。 さらに、発生したエラーのタイプを示すeVarと共に、アプリにエラー状態があることを示すデータをアドビに送信します。 入力が正しくない場合はエラーを、アプリに問題がある場合はエラーを必ず含めてください。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## デバイス機能

ほとんどのプラットフォームは、ユーザーがスポークしたデバイスを公開しませんが、デバイスの機能を公開します。 例えば、オーディオ、画面、ビデオなど。 この情報は、ユーザーとの対話時に使用できるコンテンツのタイプを定義するので役立ちます。 デバイスの機能を測定する場合は、それらを（アルファベット順に）連結することをお勧めします。

例：`":Audio:Camera:Screen:Video:"`

セグメントを作成する際に、先頭と末尾のコロンが役立ちます。 例えば、機能を持つすべてのヒットを表示 `:Audio:` します。

* [Amazon Alexaを使用するAmazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) Capabilities
* [Googleでのアクション](https://developers.google.com/actions/assistant/surface-capabilities) を使用するGoogleの機能

## 例

| ユーザー | デバイス応答 | アクション／目的 | GETリクエスト |
| --- | --- | --- | --- | ---|
| Spoofify をインストールして | レスポンスがない | Install | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Spoofify を起動して | 「OK、Spofifyを実行中」 | Play | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 楽曲を変更して | 「よし、何の曲が欲しい？」 | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 「ベイビーシャーク」を演じる | 「OK, pinkFongの「ベイビーシャーク」で遊ぶ」 | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 再生リストを変更して | 「どのプレイリストが必要？」 | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| お気に入りの曲の再生リスト | "お気に入りの曲のプレイリストを再生中" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 音楽を切って | 応答なし、音楽はオフ | Off | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
