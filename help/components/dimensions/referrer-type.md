---
title: リファラータイプ
description: 訪問者がどこから来たかに応じたリファラーのタイプ。
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
TQID: 'https://experienceleague.adobe.com/KPTS2iWls0V8I2gI0xcH1V89w0stZyVq6jWdQyEyrLY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
    internal-label: AI Tools
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b4c7365f660ff093731d55c7aba9cae5ade76789
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 47%
---
# リファラータイプ

「リファラータイプ」 [ ディメンション ](overview.md)は、訪問者がクリックしてサイトに到達した汎用チャネルをレポートします。 組織が各チャネルのルールを管理する[マーケティングチャネル](marketing-channel.md)とは異なり、各ディメンション項目のルールはアドビが管理します。

## このディメンションへのデータ入力

Adobeは、各ヒットの[ リファラー](referrer.md)からこのディメンションを取得し、Adobeの内部にある複数のルックアップテーブルと照合します。 設定する変数がありません。 各値はリファラーに依存するため、リファラーディメンションと[内部URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)が正しく設定されていることを確認してください。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（リファラーから派生） |
| **Web SDK / XDM フィールド** | なし（リファラーから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、ヒットのリファラーのタイプが含まれます。 以下に具体的な変更点を示します。

* **手動入力／ブックマーク**：ヒットのリファラーデータが存在しません。 この値には、参照元なしでリンクを開く[会話型AI ツールからの訪問が含まれます](#include-ai-traffic-that-has-no-referrer)。
* **検索エンジン**：このリファラーは、キーワードクエリ文字列を含む認識済みの検索エンジンから来ています。
* **対話型AI ツール**: リファラーは、認識された対話型AI ツールから取得されました。
* **ソーシャルネットワーク**：リファラーデータは、アドビが認識するソーシャルネットワークに属していました。
* **その他の Web サイト**：リファラーデータが、アドビが認識する検索エンジンまたはソーシャルネットワークに属していませんでした。
* **JavaScriptなし**: JavaScriptが有効になっていないブラウザーからリファラーが送信されました。
* **ハードドライブ**：リファラーは、訪問者のハードドライブ上の Web ページのローカルコピーから発生しました。
* **電子メール**：リファラーは、`imap://` または `mail://` のプロトコルを持つ URL から発生します。 オンライン電子メールサービスは、通常は `https://` プロトコルを使用するので、含まれません。

### 会話型AI ツール

>[!IMPORTANT]
>
>この値には、次のリストからリファラーを持つ訪問のみが含まれます。 ChatGPTのような一部の会話型AI ツールは、リンクを開いたときにリファラーを送信しないため、訪問は含まれません。 詳しくは、[ リファラーを持たないAI トラフィックを含める](#include-ai-traffic-that-has-no-referrer)を参照してください。

次のリストは、Adobeが使用する「対話型AI ツール」ルックアップテーブルを参照しています。 アドビは、このリストを Adobe Analytics のお客様に対して提供しています。 このリストにドメインを追加するようアドビに提案したい場合は、組織内のサポート担当デリゲートからカスタマーケアにお問い合わせください。

* `https://chatgpt.com`
* `https://chat.com`
* `https://chat.deepseek.com`
* `https://chat.openai.com`
* `https://doubao.com`
* `https://duck.ai`
* `https://gemini.google.com`
* `https://copilot.microsoft.com`
* `https://m365.cloud.microsoft`
* `https://perplexity.ai`
* `https://labs.perplexity.ai`
* `https://playground.perplexity.ai`
* `https://claude.ai`
* `https://grok.com`
* `https://komo.ai`
* `https://phind.com`
* `https://poe.com`
* `https://blackbox.ai`
* `https://chat.mistral.ai`
* `https://meta.ai`
* `https://you.com`

#### リファラーを持たないAI トラフィックを含める

ChatGPTなどの一部の会話型AI ツールは、リファラーを送信することなくリンクを開きます。 Adobeでは、「対話型AI ツール」ではなく「入力/ブックマーク済み」でこれらの訪問を報告します。 AI ツールは、リンクを開く方法をいつでも変更できます。 「会話型AI ツール」のトラフィックが減少した場合、ツールがリファラーの送信を停止した可能性があります。 この低下は、Adobe Analyticsがデータを失ったことを意味するものではありません。

リファラーの代わりに、これらのツールの一部は、開いているリンク（`utm_source=chatgpt.com`や`utm_source=perplexity`など）にUTM クエリ文字列パラメーターを追加します。 会話型AI ツールからのトラフィックの完全な数を取得するには、UTM パラメーターと「会話型AI ツール」の値を併用します。

* **変数でUTM パラメーターをキャプチャする**: eVarをランディングページ URLの`utm_source`値に設定します。 [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) プラグイン、Web SDKまたはAdobe Analytics拡張機能のURL パラメーター機能、クエリ文字列パラメーターを読み込む[処理ルール ](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)を使用します。
* **AI ツールのマーケティングチャネルを作成**：いずれかの条件がtrueの場合に一致する[ マーケティングチャネル処理ルール ](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)を作成します。 **[!UICONTROL Referrer Is Conversational AI]**&#x200B;条件と、AI ツールが使用する各値（`chatgpt.com`や`perplexity`など）に&#x200B;**[!UICONTROL クエリ文字列パラメーター]** `utm_source`条件を追加します。
* **セグメントを作成**: 「リファラータイプ」が「対話型AI ツール」に等しいか、UTM eVarにAI ツールが使用する値が含まれている[ セグメント ](/help/components/segmentation/seg-overview.md)を作成します。 [ ページ URL](page-url.md) ディメンションにはクエリ文字列が含まれているため、`utm_source=chatgpt.com`が含まれるページ URLと一致させることもできます。 このオプションは、実装を変更せずに機能します。

一部のAI ツールでは、リファラーもUTM パラメーターも送信されません。 これらのツールからのトラフィックをAI トラフィックとして特定することはできません。

### SNS

次のリストは、アドビが使用する「ソーシャルネットワーク」ルックアップテーブルを参照しています。 アドビは、このリストを Adobe Analytics のお客様に対して提供しています。 アドビがこのリストにドメインを追加することを推奨する場合は、組織のサポート委任者がサポートにお問い合わせください。

>[!NOTE]
>
>このリストは、[マーケティングチャネルの処理ルール](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)のソーシャルネットワークのデフォルトリストとは異なります。

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `bsky.app`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `go.bsky.app`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `hi5.com`
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `likeshop.me`
* `linkedin.com`
* `linkin.bio`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `threads.com`
* `threads.net`
* `tiktok.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `web-cdn.bsky.app`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `x.com`
* `xanga.com`
* `xing.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### 「その他の Web サイト」ディメンション項目の検索エンジン

「リファラータイプ」ディメンションで特定のドメインを表示する場合、「検索エンジン」の下に表示されると思われるドメインが、「その他の web サイト」の下に表示されることがあります。 例えば、「その他の Web サイト」の下に `'google.com'` が表示される場合があります。

* **「検索エンジン」ディメンション項目の検索エンジンドメイン**：このリファラーは、アドビが検索エンジンとして分類するすべての条件を満たしています。 参照ドメインは有効な検索エンジンであり&#x200B;*、*&#x200B;同時に、参照 URL にはキーワードクエリ文字列パラメーターが含まれています。
* **「その他の Web サイト」ディメンション項目の検索エンジンドメイン**：参照 URL が検索エンジンとして分類するすべての条件を満たしていませんでした。 一般的な例としては、検索以外の他の機能専用のサブドメインがあります。 例えば、`mail.google.com` または `autos.yahoo.com` は検索エンジンではなく、検索に一般的に関連付けられるトップレベルドメインに存在します。 これらのサブドメインにはキーワードクエリ文字列が含まれないので、サブドメインは「検索エンジン」ではなく「その他の Web サイト」の下に含まれます。
