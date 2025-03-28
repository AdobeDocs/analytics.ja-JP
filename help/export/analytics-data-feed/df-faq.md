---
description: Adobe Analyticsのデータフィードに関するよくある質問への回答を示します。
keywords: データフィード;ジョブ;pre列;post列;大文字と小文字を区別
title: データフィードに関する FAQ
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 0eef1b1269dcfbc7648127602bdfe24d4789f4b7
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 98%

---

# データフィードに関する FAQ

データフィードに関するよくある質問（FAQ）です。

## フィード名は一意にする必要がありますか。 {#unique}

データフィードファイル名がレポートスイート ID および日付で構成されています。同じ RSID および日付に対して設定された任意の 2 つのフィードは、同じファイル名になります。これらのフィードが同じ場所に配信されると、1 つのファイルがもう 1 つを上書きします。ファイルの上書きを防ぐには、同じ場所にある既存のフィードを上書きする可能性があるフィードを作成しないようにします。

同じファイル名を持つ別のフィードが存在する場合にフィードを作成しようとすると、エラーメッセージが表示されます。次の回避策を検討してください。

* 配信パスを変更する
* 可能であれば日付を変更する
* 可能であればレポートスイートを変更する

## データはいつ処理されますか。 {#processed}

時間別または日別のデータを処理する前に、データフィードはその時間枠（日または時間）内にデータ収集に入ったすべてのヒットがデータウェアハウスに書き出されるまで待機します。その後、データフィードはタイムスタンプがその期間内のデータを収集し、圧縮したうえで FTP 経由で送信します。時間別フィードの場合、ファイルは通常、その時間帯の終了後 15～30 分以内にデータウェアハウスに書き出されますが、設定時間はありません。その時間枠内のタイムスタンプを持つデータが存在しない場合は、同じ処理が次の時間枠で再試行されます。現在のデータフィード処理では、どのヒットがその時間帯に属しているかを確認するために `date_time` フィールドを使用します。このフィールドは、レポートスイートのタイムゾーンに基づいています。

## `post_` プレフィックスのある列と `post_` プレフィックスのない列の違いは何ですか。 {#post}

`post_` プレフィックスのない列には、データ収集に送信されたデータと完全に同じデータが含まれます。処理後の値は、`post_` プレフィックスの付いた列に格納されます。値を変更できる例としては、変数の持続性、処理ルール、VISTA ルール、通貨換算、その他のサーバー側ロジックが挙げられます。可能な限り、列の `post_` バージョンを使用することをお勧めします。

`post_` バージョンの区別のない列（`visit_num` など）は、post 列と見なすことができます。

## データフィードで大文字と小文字の区別を扱う方法 {#case}

Adobe Analytics では、ほとんどの変数は、レポートの目的で、大文字と小文字が区別されません。例えば、「snow」、「Snow」、「SNOW」、「sNow」はすべて同じ値と見なされます。大文字と小文字の区別は、データフィードで保持されます。

非 post 列と post 列の間に、値が同じで大文字と小文字が異なるバージョンがある場合（例えば、pre 列に「snow」、post 列に「Snow」）、サイトをまたいで大文字と小文字の両方の値が使用されます。post 列内のバージョンは、以前に渡されて仮想 cookie に保存されている値か、同時期にそのレポートスイート用に処理された値です。

## ボットは管理コンソールのボットルールによってフィルタリングされ、データフィードに含まれますか。 {#bots}

データフィードには、[Admin Console ボットルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html?lang=ja)でフィルタリングされたボットは含まれません。

## `event_list` または `post_event_list` データフィード列に複数の `000` 値が表示されるのはなぜですか。 {#values}

一部のスプレッドシートエディター（特に Microsoft Excel など）では、大きな数値が自動的に丸められます。`event_list` 列には、カンマで区切られた多数の数字が含まれているので、Excel で大きな数字として処理されることがあります。最後の数桁を `000` に丸めます。

Adobe では、Microsoft Excel で `hit_data.tsv` ファイルを自動的に開かないことをお勧めします。代わりに、Excel のデータのインポートダイアログボックスを使用し、すべてのフィールドがテキストとして扱われていることを確認してください。

## `hitid_high`、`hitid_low`、`visid_high`、`visid_low` などの列は、ヒットまたは訪問ごとに必ず一意になりますか？ {#hitid}

ほとんどの場合、`hitid_high` と `hitid_low` を連結することで、ヒットを一意に識別します。同じ概念が、訪問の `visid_high` と `visid_low` の連結に適用されます。ただし、処理の異常値によって 2 つのヒットが同じヒット ID を共有することはほとんどありません。 アドビでは、すべてのヒットが一意であることに依存する柔軟性のないデータフィードワークフローは作成しないことをお勧めします。

## 一部の通信事業者のドメイン列に情報が表示されないのはなぜですか。 {#domain}

一部の携帯電話会社（T-Mobile や O1 など）は、DNS 逆引き参照にドメイン情報を提供しなくなりました。そのため、そのデータはドメインレポートには使用できません。

## 7 日以上経過した古いデータから「時間別」ファイルを抽出できないのはなぜですか。 {#hourly}

作成から 7 日を超えるデータの場合、1 日の「時間別」ファイルは 1 つの「日別」ファイルに結合されます。

例：2021年3月9日に新しいデータフィードが作成され、2021年1月1日から 3 月 9 日までのデータは「時間別」として配信されます。ただし、2021年3月2日（PT）より前の「時間別」ファイルは、1 つの「日別」ファイルに結合されます。「時間別」ファイルは、作成日から 7 日未満のデータからのみ抽出できます。この場合、3 月 2 日から 3 月 9 日までです。

## 時間別データフィードへの夏時間の影響は何ですか。 {#dst}

一部のタイムゾーンでは、夏時間（DST）の規定によって時刻の変更が 1 年に 2 回行われます。データフィードでは、レポートスイートが設定されているタイム ゾーンが考慮されます。レポートスイートのタイムゾーンで DST が利用されていない場合、ファイル配信はその他すべての日と同様、通常どおりに続行されます。レポートスイートのタイムゾーンで DST が利用されている場合、時刻調整が発生する時間（通常、午前 2 時）に合わせてファイル配信の変更がおこなわれます。

標準時間（STD）から夏時間（DST）への移行時（夏時間への時計調整時）は、ユーザーの取得するファイル数が 23 個になります。DST への移行でスキップされた時間分は省略されます。例えば、移行が午前 2 時におこなわれる場合、午前 1 時のファイルの取得に続いて、午前 3 時のファイルを取得することになります。STD での午前 2 時は DST では午前 3 時になるので、午前 2 時のファイルは存在しません。

DST から STD への移行時（冬時間への時計調整時）は、ユーザーの取得するファイル数は 24 個になります。ただし、実際には移行の時間に 2 時間分のデータが含まれることになります。例えば、移行が午前 2 時におこなわれる場合、1 時間遅れて取得される午前 1 時のファイルには 2 時間分のデータが含まれています。含まれるデータは、DST での午前 1 時から STD での午前 2 時（DST の午前 3 時に該当）までのものです。次のファイルは STD での午前 2 時から開始されます。

## Analytics は FTP 転送エラーをどのように処理しますか。 {#ftp-failure}

FTP 転送が失敗した場合（ログイン拒否、接続の切断、割り当て不足エラー、その他の問題が原因）、Adobe は自動的に接続を試み、データを最大 3 回送信しようとします。それでもエラーが発生する場合、フィードは失敗とマークされ、電子メール通知が送信されます。

転送が失敗した場合は、正常に実行されるまでジョブを再実行できます。

FTP サイトにデータフィードを表示する際に問題が発生した場合は、 [データフィードのトラブルシューティング](troubleshooting.md) を参照してください。

## ジョブを再送する方法を教えてください。 {#resend}

配信の問題を確認および修正したら、ジョブを再実行してファイルを取得します。

## Amazon S3 データフィードの BucketOwnerFullControl 設定とは何ですか。 {#BucketOwnerFullControl}

**BucketOwnerFullControl** は、他のバケットにオブジェクトを作成するためのクロスアカウント権限を付与します。

Amazon S3 の一般的な使用例では、Amazon Web サービス（AWS）アカウント所有者がバケットを作成し、次にそのバケット内でオブジェクトを作成する権限を持つユーザーを作成し、そのユーザーに資格情報を付与します。この場合、ユーザーのオブジェクトは、同じアカウントに属し、アカウント所有者は黙示的にそのオブジェクトのフルコントロール権（読み取り、削除など）を持ちます。この処理は、FTP の配信の仕組みと似ています。

AWS でも、異なるユーザーアカウントに属するバケット内にオブジェクトを作成できます。例えば、2 人の AWS ユーザー（userA と userB）が同じ AWS アカウントに属しておらず、他のバケットにオブジェクトを作成したいとします。userA が「bucketA」というバケットを作成すると、バケットの所有者でない userB に対して、bucketA でのオブジェクト作成を明示的に許可するバケット ポリシーを作成できます。このポリシーには、userA と userB が資格情報を交換する必要がないというメリットがあります。代わりに、userB は、userA にアカウント番号を提供し、userA は基本的に「userB に bucketA 内でオブジェクトを作成させる」ということを指示するバケットポリシーを作成します。

ただし、オブジェクトは親バケットから権限を継承しません。userB が userA のバケットにオブジェクトをアップロードする場合、userB は依然としてそのオブジェクトを「所有」します。userA はバケットを所有していますが、デフォルトでは、そのオブジェクトに対するいかなる権限も付与されていません。UserB は依然としてオブジェクトの所有者なので、userB が userA に明示的に権限を付与する必要があります。この権限を付与するには、userB は、BucketOwnerFullControl ACL を使用してオブジェクトをアップロードする必要があります。この ACL は、オブジェクトが userB によって「所有」されている場合でも、バケットの所有者（userA）にオブジェクトに対する完全な権限（読み取り、書き込み、削除など）を付与します。

>[!NOTE]
>
>Adobe Analytics は、バケットの所有者に新しいオブジェクの完全な制御を許可する必要があるポリシーがバケットに含まれているかどうか、またはバケットがデータを書き込むユーザーとは異なるアカウントに属しているかどうかを判断しません。代わりに、Analytics は、フィードのアップロードごとに、バケットの所有者を `BucketOwnerFullControl` ACL に自動的に追加します。

