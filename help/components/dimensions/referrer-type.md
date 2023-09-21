---
title: リファラータイプ
description: 転送者のタイプ。訪問者の送信元に応じて異なります。
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 96%

---

# リファラータイプ

「リファラータイプ」 [ディメンション](overview.md) は、訪問者がクリックスルーしてサイトに到達した汎用チャネルをレポートします。 組織が各チャネルのルールを管理する[マーケティングチャネル](marketing-channel.md)とは異なり、各ディメンション項目のルールはアドビが管理します。

## このディメンションへのデータ入力

このディメンションは、アドビ内部の複数のルックアップテーブルを参照します。各値は、ヒットの[リファラー](referrer.md)（[内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)に依存）に基づきます。リファラーディメンションと内部 URL フィルターが正しく設定されていることを確認します。

## ディメンション項目

ディメンション項目には、ヒットのリファラーのタイプが含まれます。以下に具体的な変更点を示します。

* **手動入力／ブックマーク**：ヒットのリファラーデータが存在しません。
* **検索エンジン**：このリファラーは、キーワードクエリ文字列を含む認識済みの検索エンジンから来ています。
* **ソーシャルネットワーク**：リファラーデータは、アドビが認識するソーシャルネットワークに属していました。
* **その他の Web サイト**：リファラーデータが、アドビが認識する検索エンジンまたはソーシャルネットワークに属していませんでした。
* **ハードドライブ**：リファラーは、訪問者のハードドライブ上の Web ページのローカルコピーから発生しました。
* **電子メール**：リファラーは、`imap://` または `mail://` のプロトコルを持つ URL から発生します。オンライン電子メールサービスは、通常は `https://` プロトコルを使用するので、含まれません。

### SNS

次のリストは、アドビが使用する「ソーシャルネットワーク」ルックアップテーブルを参照しています。アドビは、このリストを Adobe Analytics のお客様に対して提供しています。アドビがこのリストにドメインを追加することを推奨する場合は、組織のサポート委任者がサポートにお問い合わせください。

>[!NOTE]
>
>このリストは、[マーケティングチャネルの処理ルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)のソーシャルネットワークのデフォルトリストとは異なります。

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
* `linkedin.com`
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
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
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

「リファラータイプ」ディメンションで特定のドメインを表示する場合、「その他の Web サイト」の代わりに「検索エンジン」の下に予期されるドメインが存在する可能性があります。例えば、「その他の Web サイト」の下に `'google.com'` が表示される場合があります。

* **「検索エンジン」ディメンション項目の検索エンジンドメイン**：このリファラーは、アドビが検索エンジンとして分類するすべての条件を満たしています。参照ドメインは有効な検索エンジンであり&#x200B;*、*&#x200B;同時に、参照 URL にはキーワードクエリ文字列パラメーターが含まれています。
* **「その他の Web サイト」ディメンション項目の検索エンジンドメイン**：参照 URL が検索エンジンとして分類するすべての条件を満たしていませんでした。一般的な例としては、検索以外の他の機能専用のサブドメインがあります。例えば、`mail.google.com` または `autos.yahoo.com` は検索エンジンではなく、検索に一般的に関連付けられるトップレベルドメインに存在します。これらのサブドメインにはキーワードクエリ文字列が含まれないので、サブドメインは「検索エンジン」ではなく「その他の Web サイト」の下に含まれます。
