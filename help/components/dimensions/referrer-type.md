---
title: リファラータイプ
description: 転送者のタイプ。訪問者の送信元に応じて異なります。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# リファラータイプ

「転送者タイプ」ディメンションは、訪問者がクリックスルーしてサイトに到着した汎用チャネルをレポートします。 アドビは、 [マーケティングチャネルとは異なり、各ディメンション値のルールを管理します。](marketing-channel.md)マーケティングチャネルでは、組織が各のルールを管理します。

## このディメンションにデータを入力する

このディメンションは、Adobe内部の複数の参照テーブルを参照します。 各値は、ヒットの [転送者](referrer.md) ( [内部URLフィルターに依存)に基づきます](/help/admin/admin/internal-url-filter-admin.md)。 転送者ディメンションと内部URLフィルターが正しく設定されていることを確認します。

## 分析コード値

ディメンション値には、ヒットの転送者のタイプが含まれます。 具体的な値は次のとおりです。

* **手動入力/ブックマーク**: ヒットの転送者データが存在しません。
* **検索エンジン**: この転送者は、キーワードクエリ文字列を含む認識済みの検索エンジンから来ています。
* **ソーシャルネットワーク：**: 転送者データは、アドビが認識するソーシャルネットワークに属していました。
* **その他のWebサイト**: 転送者データが、アドビが認識する検索エンジンまたはソーシャルネットワークに属していませんでした。
* **ハードドライブ**: 転送者は、訪問者のハードドライブ上のWebページのローカルコピーから発生しました。
* **電子メール**: 転送者は、またはのプロトコルを持つURLから発生 `imap://` し `mail://`ます。 オンライン電子メールサービスは、通常はプロトコルを使用するので、含まれません `https://` 。

### ソーシャルネットワーク

次のリストは、アドビが使用する「ソーシャルネットワーク」参照テーブルを参照しています。 アドビは、このリストをアドビAnalyticsのお客様に対して提供しています。 アドビがこのリストにドメインを追加することを推奨する場合は、組織のサポート委任者がカスタマーケアにお問い合わせください。

>[!NOTE]
>
>このリストは、マー [ケティングチャネルの処理ルールのソーシャルネットワークのデフォルトリストとは異なります](../c-marketing-channels/c-rules.md)。

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `yozm.daum.net`
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
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
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
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
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
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### 「その他のWebサイト」ディメンション値の検索エンジン

「転送者タイプ」ディメンションで特定のドメインを表示する場合、「その他のWebサイト」の代わりに「検索エンジン」の下に予期されるドメインが存在する可能性があります。 例えば、「その他のWebサイト」の下に `'google.com'` 表示される場合があります。

* **[検索エンジン]ディメンション値の検索エンジンドメイン**: この転送者は、アドビが検索エンジンとして分類するすべての条件を満たしています。 参照ドメインは有効な検索エンジンで *あり* 、参照URLにはキーワードクエリ文字列パラメータが含まれています。
* **「その他のWebサイト」ディメンション値の検索エンジンドメイン**: 参照URLが検索エンジンとして分類するすべての条件を満たしていませんでした。 一般的な例としては、検索以外の他の機能専用のサブドメインがあります。 例えば、 `mail.google.com` またはは検索エンジンで `autos.yahoo.com` はなく、検索に一般的に関連付けられるトップレベルドメインに存在します。 これらのサブドメインにはキーワードクエリ文字列が含まれないので、サブドメインは「検索エンジン」ではなく「その他のWebサイト」の下に含まれます。
