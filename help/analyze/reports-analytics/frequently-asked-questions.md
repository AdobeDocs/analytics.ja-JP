---
description: Analytics に関して最もよくある質問に対する回答とトラブルシューティングの提案を示します。
keywords: Analytics のトラブルシューティング
title: Reports & Analytics に関するよくある質問 (FAQ)
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 99702728-971f-484a-91f5-f3210b89485c
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# よくある質問

Reports &amp; Analytics の Analytics に関して最もよくある質問に対する回答とトラブルシューティングの提案を示します。実装に関するよくある質問については、『実装マニュアル』の「[FAQ](/help/implement/faq.md)」を参照してください。

>[!IMPORTANT]
>**2023 年 12 月 31 日**（PT）をもって、アドビは Reports &amp; Analytics およびそれに付随するレポートと機能を廃止する予定です。その時点で、Reports &amp; Analytics およびそのすべてのレポートとスケジュールは機能を停止します。 Reports &amp; Analytics を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。Reports &amp; Analytics のほとんどの機能は、Analysis Workspace 内で使用できます。 2015年の Analysis Workspace のリリース以降、Reports &amp; Analytics の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。このお知らせでは、提供終了プロセスについて説明します。

**ロックされたマイアカウントのロックを解除する方法を教えてください。**

アカウントを再アクティブ化するには、組織内の管理者に問い合わせてください。『Technotes マニュアル』の「[Adobe Analytics でのログインに関する問題のトラブルシューティング](/help/technotes/troubleshoot-login.md)」も参照してください。

**データが収集されているのに空白のレポートが表示されるのはなぜですか。**

レポートデータのトラブルシューティングには、次の点を確認する必要があります。

* 使用されている指標を確認します。一部のレポートは、Reports &amp; Analytics ではデフォルトで売上高に設定されます。表示している指標がレポートに関連していることを確認します。
* 日付範囲を確認します。特に、組織のデータ保持ポリシーを超える日付範囲のデータは返されません。日付範囲が正しく設定されていることを確認します。
* 内部 URL フィルターを確認します。一部のトラフィックソースレポートは、内部 URL フィルターを正しく定義するまで機能しません。

**ナビゲーションメニューに一部のレポートが表示されないのはなぜですか。**

レポートがメニューに表示されない最も一般的な理由は、権限の制限またはメニューのカスタマイズです。組織内の製品管理者に問い合わせて、必要なすべてのディメンションと指標にアクセスできること、また、レポートスイートのメニュー構造がカスタマイズされていないことを確認します。

**長い値が切れている理由を教えてください。**

Adobe Analytics ではほとんどの変数に文字数の上限があります。ページ名の上限は 100 文字で、カスタムコンバージョン変数（eVar）の上限は 255 文字です。切り捨てを防ぐため、アドビに送信する値は簡潔にすることをお勧めします。

**レポートに大きな遅れが生じる理由を教えてください。**

リアルタイムレポートでは、一部のトラフィック指標は数分で入手できますが、コンバージョンデータや、処理量の多いその他のデータを入手するには通常 30 ～ 90 分かかります。Experience Cloud プラットフォームは堅牢ですが、いくつかの状況下ではレポートに遅延が生じることがあります。この遅延は、レイテンシーと呼ばれます。詳細については、『管理者マニュアル』の「[レイテンシー](/help/technotes/latency.md)」を参照してください。

**iPhone でデバイスのバージョンが表示されない理由を教えてください。**

iOS デバイスでは、デバイスバージョンではなく、ユーザーエージェント文字列のファームウェアバージョンが表示されます。Adobe Analytics で利用できる情報を使用して iPhone デバイスのバージョンを判断するのは困難です。詳しくは、Analytics KB で [iPhone デバイスバージョンの比較](https://helpx.adobe.com/jp/analytics/kb/comparing-iphone-device-versions.html)を参照してください。

**レポートの一番下の合計が値の和と一致しない理由を教えてください。**

ディメンション項目はよく複数の場所に適用されることがあります。例えば、午前 0 時にまたがる訪問や、単一の注文に属する複数の製品の訪問などです。ディメンション項目は、該当するすべての行項目にわたってレポートされますが、レポートの合計では重複が除外されます。詳しくは、Analytics KB で[行項目の合計とレポートでの合計の比較](https://helpx.adobe.com/jp/analytics/kb/sum-line-items-different-from-total.html)を参照してください。

**レポートスイートの特定の IP アドレスからデータを除外する方法を教えてください。**

レポートから、サイトのテストや従業員の使用などの社内の Web サイト活動のデータを排除できます。この機能により、自身や会社の同僚はトラフィックデータを歪曲することなく、自社サイトを訪問することができます。詳細については、『管理者マニュアル』の「[IP アドレスの除外](/help/admin/admin/exclude-ip.md)」を参照してください。

**レポートスイートを削除できますか。**

レポートスイートを削除することはできません。ただし、Adobe Analytics のすべてのビューでレポートスイートを非表示にすることはできます。非表示のレポートスイートに送信されるサーバーコールは、引き続き月間契約の上限にカウントされます。詳しくは、『管理者マニュアル』の「[レポートスイートを非表示にする](/help/admin/company/c-hide-report-suites.md)」を参照してください。

**セグメント化を使用する場合は、どのコンテナを使用する必要がありますか（ページビュー、訪問、訪問者）。**

使用するセグメントコンテナは、データを取り込む範囲に応じて異なります。ページビューコンテナは、セグメント条件に一致するヒットのみを取り込みます。これは、訪問の無関係な部分をフィルタリングして除外するのに役立ちます。訪問コンテナは、1 つ以上のヒットがセグメント条件に一致する訪問のすべてのヒットを取り込みます。これは、一般的にセッションを調べるのに役立ちます。訪問者コンテナは、ヒットがセグメント条件に一致した訪問をすべて取り込み、訪問者を調べるのに役立ちます。どのセグメントコンテナを使用するのが最適かを判断するのは、アナリストとしてあなたが選択できます。詳しくは、『コンポーネントマニュアル』の「[セグメントの概要](/help/components/segmentation/seg-overview.md)」を参照してください。

**セグメントが Data Warehouse に表示されないのはなぜですか。**

Data Warehouse 固有の処理アーキテクチャにより、プラットフォームは、パスなど、一部のタイプのデータを処理するように最適化されていません。詳しくは、『コンポーネントマニュアル』の「[Data Warehouse セグメントの互換性](/help/components/segmentation/seg-reference/seg-compatibility.md)」を参照してください。
