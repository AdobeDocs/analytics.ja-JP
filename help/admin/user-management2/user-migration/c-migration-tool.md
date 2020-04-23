---
description: Analytics ユーザー ID を Adobe Experience Cloud 内の Admin Console に移行するプロセスについて説明します。
title: Admin Console への Analytics ユーザーの移行
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Admin Console への Analytics ユーザーの移行 {#analytics-user-migration-to-the-admin-console}

Analytics ユーザー ID を Adobe Experience Cloud 内の Admin Console に移行するプロセスについて説明します。

Admin Console に関する一般的な（Analytics の移行に関連しない）ヘルプについては、『[Admin Console ユーザーガイド](https://helpx.adobe.com/jp/enterprise/administering/user-guide.html)』を参照してください。

移行後は、管理コンソール [でExperience Cloudのユーザーと製品を](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/admin-getting-started.html) 「管理」できます。

## AnalyticsユーザーIDの移行とは何ですか。 {#section-adbe49aba10c4e62afa836a97894107c}

AnalyticsユーザーIDの移行により、管理者はAnalyticsユーザー管理のユーザーアカウントをAdobe管理コンソールに簡単に移行できます。 ユーザーを移行すると、Experience Cloudで利用可能なソリューションおよびコアサービスにアクセスできるようになります。 移行は、段階的にお客様に展開されています。

管理コンソールを使用する利点は次のとおりです。

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> メリット </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>シングルサインオン </p> </td> 
   <td colname="col2"> <p>Analytics ユーザーは、Adobe ID または Enterprise ID を使用して、Experience Cloud のすべてのソリューションにログインできるようになります。このログインにより、Experience Cloud で統合されたソリューションおよびコアサービスにアクセスできます。 </p> <p>移行後、従来のログイン（<span class="filepath">my.omniture.com</span> および <span class="filepath">sc.omniture.com</span>）でログインしようとするユーザーは、<span class="filepath">experiencecloud.adobe.com</span> にリダイレクトされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー ID および権限の管理 </p> </td> 
   <td colname="col2"> <p>Analytics 管理者は、<a href="http://adminconsole.adobe.com/enterprise/">Admin Console</a>（http://adminconsole.adobe.com/enterprise/）でのみユーザーと権限を管理できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>製品とコアサービスの管理 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">新しいユーザーの招待 </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">製品プロファイル </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">特定の製品やサービスに対する権限をユーザーに付与する </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Adobe Experience Cloud で使用可能な<a href="https://docs.adobe.com/content/help/ja-JP/core-services/interface/experience-cloud.html">クロスソリューションコアサービス</a>へのアクセス権を獲得できます。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## ユーザー ID の移行前に知っておくべき情報（およびすべきこと）（FAQ） {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

移行前に考えられる質問と、それに対する回答を示します。

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問/タスク </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Analytics管理者で、移行前の電子メールを受け取りました。 最初に何をすればいいの？ </p> </td> 
   <td colname="col2"> <p>自分が Adobe ID を持っていて、<a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a> にアクセスできることを確認してください。 </p> <p>アクセスできない場合は、<a href="https://helpx.adobe.com/jp/marketing-cloud/contact-support.html">アドビカスタマーケア</a>に連絡してください（まず、Analytics 管理者を適切な組織に招待できるシステム管理者または製品管理者に連絡してください）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AnalyticsとのAEMの統合 </p> </td> 
   <td colname="col2"> <p> Analyticsと統合されたAEMユーザーは、パスワードの代わりにAnalyticsの共有暗号鍵を使用するように設定を変更する必要があります。 </p> <p> 移行を有効にする前に、この操作を行う必要があります。 移行が無効になると、元々設定されていたパスワードは無効になります。 </p> <p><b>AnalyticsでShared Secretを取得するには</b> </p> <p> 共有暗号鍵は Analytics （<span class="uicontrol">分析</span>／<span class="uicontrol">User Management</span>）から取得でき、各ユーザーで異なります。 </p> <p><b>共有暗号鍵を使用して AEM 設定を更新するには</b> </p> <p><a href="https://helpx.adobe.com/jp/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">Adobe Analytics への接続とフレームワークの作成</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Builder の更新 </p> </td> 
   <td colname="col2"> <p> <p>重要：<a href="https://marketing.adobe.com/resources/help/ja_JP/arb/t_install_arb.html">Report Builder</a> のインストールを最新バージョンに更新してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行はいつ開始されますか。 </p> </td> 
   <td colname="col2"> <p>アドビは、いつ移行が開始されるかについての手順を電子メールでAnalytics管理者に通知します。 </p> <p>管理コンソールへの移行は、ウェーブで行われます。 移行日に、AdobeはAnalytics管理者に通知し、移行ツールへのアクセスを許可します。 ログイン会社が各移行ウェーブに対して定義された条件を満たした後、アドビは次のことを行います。 </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">移行の開始と終了日を設定します。 </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">移行の約30日前に、会社の現在のAnalytics管理者に電子メール通知を送信します。 </li> 
     <li id="li_476265B24CE2404B995201170C75D674">移行の開始日を管理者に通知する製品内通知を表示します。 </li> 
    </ul> <p> 移行の日に、以前の権限グループが管理コンソールに自動的にコピーされます。 Analytics 管理ツールで新規ユーザーを招待したり、新規グループを作成したりできなくなります。 </p> <p>移行後： </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">管理者は、管理コンソールを使用してAnalyticsのユーザーと権限を管理します。 （Analytics/管理者/ユーザー管理で、ユーザー管理インターフェイスを使用しなくなります）。 </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">ユーザーは、<span class="filepath">my.omniture.com</span> ではなく、Experience Cloud から Adobe ID または Enterprise ID を使用して Analytics にアクセスするようになります。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行の開始日はどうなりますか。 </p> </td> 
   <td colname="col2"> <p>移行の開始日のUTC午前10時： </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Analyticsの既存の権限グループは、製品プロファイルとして管理コンソールに自動的に複製されます。レポートスイート、指標、ディメンション、Analyticsおよびレポートスイートツールの説明や詳細な権限が含まれます。 </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">現在のAnalyticsユーザーのうち、管理コンソールで作成したユーザー（つまり、Adobe/Enterprise IDがリンクされているユーザー）は、管理コンソールの適切な製品プロファイルに追加されます。 </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Analyticsの「管理者」タブの「ユーザー管理」セクションが読み取り専用 <span class="term"> に設定されます</span>。 ここで新規ユーザーおよび権限グループを作成することはできなくなり、これらの機能は Admin Console で実行することになります。詳細については、<a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Admin Console でサポートされない Analytics の機能</a>を参照してください。 </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">管理者には、ユーザID移行ツールへのアクセス権 <a href="https://marketing.adobe.com/resources/help/ja_JP/experience-cloud/admin-console/analytics-migration/t_migrate-users.html">が付与されます</a>。 また、製品内の通知が表示され、移行の終了日（通常は60日後）と、ヘルプコンテンツおよびFAQへのリンクが示されます。 </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">管理コンソールの「権限」タブに対するアクセス権が付与され、Analyticsで使い慣れたすべての詳細なオプションを使用して製品プロファイルを作成できます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザーIDを移行する方法を教えてください。 </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. 管理コンソールで、ユーザーを製品プロファイルに追加する（Analyticsの権限グループから複製される）には、このツールを使用します。 ユーザーIDは、自分のペースで移行できます。 </p> <p>管理権限が必要です。 移行が完了すると、元に戻すことはできません。 </p> <p>移行終了日になると、ログイン会社内のユーザーの <span class="filepath">my.omniture.com</span> へのアクセス権が無効になります。ユーザー（まだ移行されていないユーザーを含む）は、新しい Experience Cloud URL（<span class="filepath">experiencecloud.adobe.com</span>）にリダイレクトされます。 </p> <p>注意：移行前に、ユーザーおよびグループを監査することをお勧めします。古い未使用のアカウントや、製品へのアクセス権を持つべきではなくなっているアカウント（もう組織にいない従業員など）を削除してください。 </p> <p>関連トピック：<a href="/help/admin/user-management2/user-migration/migrate-enterprise.md">Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行は、Analyticsの実装に影響を与えますか。それとも、データの収集方法に影響を与えますか。 </p> </td> 
   <td colname="col2"> <p>いいえ。 </p> <p>移行ツールは、ユーザー ID と権限を Analytics のユーザー管理から <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a> に移行するためのものです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行プロセスにはどのくらいの時間がかかりますか。 </p> </td> 
   <td colname="col2"> <p>移行前の4週間前に、現在のAnalytics管理者全員に移行前の通知の電子メールが届きます。 (実際の開始日がAnalyticsインターフェイスに表示されます)。 </p> <p>移行が始まると、管理者はプロセスを完了するのに60日かかります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行を迅速に行うことはできますか。 </p> </td> 
   <td colname="col2"> <p>はい。ただし、移行が開始される前の時間を次のように使用することをお勧めします。 </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">管理コンソールで、Analytics製品管理者であることを確認します。 </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">移行が始まるとログインエクスペリエンスが変わることをユーザーベースに伝えます。 </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">現在のユーザーと権限を監査し、クリーンアップアクティビティを実行 </li> 
    </ul> <p>移行を早めるには、<a href="https://helpx.adobe.com/jp/marketing-cloud/contact-support.html">アドビカスタマーケア</a>でカスタマーサクセスマネージャーに連絡し、開始日を早めるように依頼を送信します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 管理コンソールにアクセスできないAnalytics管理者です。 管理コンソールにアクセスするのに役立つのは誰ですか？ </p> </td> 
   <td colname="col2"> <p>組織の Admin Console へのアクセス権を持つシステム管理者または製品管理者であれば、Analytics 管理者にアクセス権を付与できます。組織内で誰が Admin Console の管理者権限を持っているかわからない場合は、<a href="https://helpx.adobe.com/jp/marketing-cloud/contact-support.html">アドビカスタマーケア</a>にお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行開始日を延期できますか。 </p> </td> 
   <td colname="col2"> <p>はい。<a href="https://helpx.adobe.com/jp/marketing-cloud/contact-support.html">アドビカスタマーケア</a>に連絡してください。 </p> 
    <draft-comment> 
     <p>開始日における現在の Analytics ユーザーおよび権限管理に対する変更の説明については、以下を参照してください。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>会社を管理コンソールに移行しました。移行の開始日より前に、新しいユーザーおよび権限グループを作成する方法を教えてください。 </p> </td> 
   <td colname="col2"> <p>移行の開始日より前に、管理コンソールまたはAnalytics/ユーザー管理でユーザーを作成できます。 </p> <p>移行が開始された後は、管理コンソールでのみユーザーおよび権限グループを作成できます。 </p> 
    <draft-comment> 
     <p>移行開始日に発生する処理の詳細については、以下の「移行」の節を参照してください。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Federated IDを使用してシングルサインオンを実装できるのはいつですか。 </p> </td> 
   <td colname="col2"> <p> Admin Consoleでは、IDタイプをAdobe IDからFederated IDに変更できるツールが近日中に利用可能になります。 移行中は、ユーザーをFederated IDとして移行できません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移行時に知っておくべきこと(FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

移行プロセスと、移行プロセスが現在のユーザー管理に与える影響に関する重要な情報です。

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>管理コンソールには、権限グループはどのように複製されますか。 ユーザーは？ </p> </td> 
   <td colname="col2"> <p>移行された Analytics グループは、Admin Console では<i>製品プロファイル</i>と呼ばれます。元のグループの権限設定は、移行時に保持されます。 ただし、グループに割り当てられたユーザーは移行されません。 移行ツールを使用して、そのグループに属するユーザーが移行されると、そのユーザーはその製品のユーザーに割り当てられます。プロファイル </p> <p>例えば、メンバーにReport Builderおよび分析ワークスペース（一部のレポートスイート、指標、ディメンション）の権利を付与したWest Coast Operations権限グループは、West Coast Operations製品プロファイルになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行作業を別の管理者に委任できますか。 </p> </td> 
   <td colname="col2"> <p>移行が始まると、Experience Cloudを介してAnalyticsインスタンスにアクセスする管理者は、移行ツールを使用してユーザーの移行を開始（または続行）できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行されていないユーザーの権限グループのメンバーシップを更新できますか。 </p> </td> 
   <td colname="col2"> <p>はい。Analyticsのユーザー管理セクション内で、移行されていないユーザーのグループメンバーシップを変更できます。 </p> 
    <draft-comment> 
     <p>これをどこで行うかについては、Ashok の確認待ち。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行開始後にAnalyticsでユーザーと権限グループを作成し、移行ツールを使用して管理コンソールに移行できますか。 </p> </td> 
   <td colname="col2"> <p> いいえ。移行が始まると、新しいプロファイルおよび権限グループ（管理コンソールの「製品ユーザー」と呼ばれる）は、すべて管理コンソールで作成する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行ツールを使用して移行したユーザーには、Analyticsでの権限と同じ権限が割り当てられますか。 </p> </td> 
   <td colname="col2"> <p>はい。ツールを使用して移行されたユーザーには、現在Analyticsで持っている権限が付与されます。 さらに、Experience Cloudを介してAnalyticsにアクセスする際に、Analyticsアセット（セグメント、プロジェクト、計算指標など）へのアクセス権を保持します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console に移行されたユーザーは、引き続き <span class="filepath">my.omniture.com</span> を使用して Analytics にアクセスできますか。 </p> </td> 
   <td colname="col2"> <p>はい。移行ツールで従来のログインアクセスを無効にしない限り、移行されたユーザーは、移行終了日まで既存のユーザー名とパスワードを使用して <span class="filepath">my.omniture.com</span> で引き続き Analytics にアクセスできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2人以上のユーザーのAnalyticsレコードに同じ電子メールIDが存在する。 移行するとどうなりますか。 </p> </td> 
   <td colname="col2"> <p>管理コンソールの重複アカウントでは一意の電子メールIDが必要なので、これらのユーザーを複数移行しようとすると、「ユーザーの電子メールID」エラーが発生します。 移行を再試行する前に、「ユーザー管理（従来の方法）」セクションで、移行されていないユーザーの電子メールIDを更新できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ユーザーの移行後に行う操作 </p> </td> 
   <td colname="col2"> <p><span class="filepath">my.omniture.com</span> への従来のログインアクセスを無効にしてください。レガシーログインは、移行されない限り無効にできません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行プロセスを追跡できますか。 </p> </td> 
   <td colname="col2"> <p>移行ツールには、移行に成功したダッシュボードの数と、従来のログインが無効になっているユーザの数を示すユーザが含まれています。 </p> <p> 100%のユーザーが移行を完了し、従来のログインを無効にした場合に、ログイン会社を管理コンソールに正常に移行できるのが理想的です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行中にユーザーと権限の管理を実行する必要がある。 このツールを使用して実行できるタスク </p> </td> 
   <td colname="col2"> <p>移行が始まったら、管理コンソールを使用して、新しいユーザーと製品のプロファイルを作成し、 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ツールを使用して移行した場合、ユーザーはどのような体験をするか。 </p> </td> 
   <td colname="col2"> <p>Analyticsユーザーレコードの電子メールIDに宛てられたお知らせの電子メールが届き、Experience Cloudを介してAnalyticsにアクセスする新しい方法について通知されます。 既存のAdobe IDがない場合は、Adobe IDを作成するように求められ、その後、Adobe IDを使用してソリューションにアクセスできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行ツールを使用する代わりに、APIを使用してユーザーを移行できますか。 </p> </td> 
   <td colname="col2"> <p>いいえ。移行ツールを使用して、既存のすべてのユーザーが管理コンソールに移行されることを確認する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理コンソールで利用できないAnalyticsのユーザー管理機能は何ですか。 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">資産の転送 </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">ユーザーの有効期限 </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">ユーザーログ </li> 
    </ul> <p>これらは、引き続きAnalyticsユーザー管理で使用できます。 </p> <p>詳細については、<a href="/help/admin/user-management2/user-migration/c-migration-tool.md">Admin Console でサポートされない Analytics の機能</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理コンソールで複数の設定を作成し、Analytics権限グループにマッピングしました。 移行が始まると、これらの設定はどうなりますか。 </p> </td> 
   <td colname="col2"> <p>Analytics権限グループは、他のすべてのグループと同様に、製品プロファイルとして管理コンソールで再作成されます。 つまり、基本的に製品の権限を持つ2つのプロファイルがコンソールに表示されることになります。重複の権限を持つ製品の場合。 管理コンソールから重複製品プロファイルを削除できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザーの移行後の次の手順は何ですか。 </p> </td> 
   <td colname="col2"> <p>1 人または複数のユーザーを移行したら、次のステップは <span class="filepath">my.omniture.com</span> での従来のログインを無効にすることです。これを行うには、移行ツールでこれらのユーザを選択し、画面の上部に表示されるコンテキストに応じた「レガシーログインを無効にする」オプションをクリックします。 このオプションは、すべてが管理コンソールに正常に移行されたユーザまたはユーザのセットを選択した場合にのみ表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行の終了日に何が起きますか。 </p> </td> 
   <td colname="col2"> <p>移行の終了日(移行の開始から60日後)を過ぎると、ログイン会社内のすべてのユーザーは、Adobe IDを使用して、Experience Cloudログインページを介してログインにリダイレクトされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行の終了日までにすべてのユーザーを移行できない。 移行されなかったユーザーはAnalyticsにアクセスできなくなりますか。 </p> </td> 
   <td colname="col2"> <p>終了日までに移行されなかったユーザーは、Experience Cloud のログインページ（experiencecloud.adobe.com）にリダイレクトされ、Analytics にアクセスできなくなります。ただし、Analytics 管理者は引き続き移行ツールにアクセスできるので、ユーザーを探して移行し、アクセス権を復元することができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移行後の知識(FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問/問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>管理コンソールからのユーザーの削除 </p> </td> 
   <td colname="col2"> <p> Analyticsでは、削除されたユーザーは有効期限切れに設定され <span class="term"> ます</span>が、アカウントは引き続き存在します。 アカウントを保持すると、セグメント、計算指標、予定レポート、プロジェクトなどのアセットを転送できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アカウントの有効期限 </p> </td> 
   <td colname="col2"> <p> 管理ツールで、Analyticsでアカウントの有効期限を手動で設定できます。 有効期限が切れると、ユーザーはAnalyticsにアクセスできなくなりますが、実際のExperience Cloudユーザーアカウント（Adobe ID、Enterprise ID、Federated IDなど）はが期限切れにならない。 引き続きExperience Cloudにログインでき、Analyticsにクリックすることはできません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Admin Console でサポートされない Analytics の機能 {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>移行中に問題になる可能性があるので、必ず以下の事項を確認してください。

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問/問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ログイン名 </p> </td> 
   <td colname="col2"> <p> 管理コンソールに移行する管理者は、「ログインユーザー」機能を使用して、管理コンソールに移行された管理者以外のユーザーアカウントにアクセスできなくなります。 この機能は、Analyticsで非推奨となっています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザーの有効期限とアセットの転送 </p> </td> 
   <td colname="col2"> <p> 管理コンソールは、ユーザーの有効期限やアセットの転送をサポートしていません。 管理者は、両方の機能に対して、Analyticsの管理ツールの「Analyticsユーザーとアセット」セクションを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最終アクセス（最後のログイン） </p> </td> 
   <td colname="col2"> <p> ユーザーの最終ログイン日時に関する詳細は、管理コンソールではなく、「Analyticsユーザーとアセット」リンクで利用できます。 Analytics の最終ログイン日は、ユーザーが Experience Cloud 内から実際にいつ Analytics にアクセスしたかによって特定されるもので、Experience Cloud にログインした日時を反映しているわけではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー管理 API の<a href="https://helpx.adobe.com/jp/enterprise/help/identity.html">アドビがサポートしている ID タイプ</a> </p> </td> 
   <td colname="col2"> <p> Admin Console への移行をおこなっている管理者は、プログラムによって Admin Console のユーザーアカウントにアクセスできるよう、Adobe I/O で提供されている<a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">ユーザー管理 API</a> を設定する必要があります。 </p> <p>移行を有効にすると、Analytics権限APIは無効になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ウェブ サービス資格情報 </p> </td> 
   <td colname="col2"> <p> ユーザーのWebサービスの資格情報（およびその共有暗号鍵）は管理コンソールでは使用できず、「Analyticsのユーザーとアセット」セクションから特定のユーザーをクリックしてアクセスできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>シングルサインオン </p> </td> 
   <td colname="col2"> <p> 移行が完了すると、Analyticsのシングルサインオン設定は削除されます。 移行中もアクティブな状態が維持されます。 Analytics のシングルサインオンを使用する顧客は、<a href="https://helpx.adobe.com/jp/enterprise/help/identity.html">Adobe Federated ID</a> にアップグレードする必要があります。 </p> <p>Analyticsでは、まずAdobe IDとしてユーザーを移行し、Experience Cloudアカウントを簡単に作成してから、それらのアカウントをフェデレーテッドシングルサインユーザーに変換することをお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>権限グループのダウンロード </p> </td> 
   <td colname="col2"> <p> 権限グループ情報のダウンロードは、Analytics管理ツールまたはAdobe管理コンソールではサポートされなくなります。 ユーザーは、adobe.ioのユーザー管理APIを使用して、権限グループ情報を一括で取得する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アカウント作成日 </p> </td> 
   <td colname="col2"> <p>アカウント作成日の情報は、Analytics管理ツールまたはAdobe管理コンソールではサポートされなくなりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>一括電子メール </p> </td> 
   <td colname="col2"> <p>ユーザーへの一括電子メールは、Analytics管理コンソールまたはAdobe管理コンソールではサポートされなくなります。 お客様は、ユーザーの電子メールアドレスをアドビの管理コンソールから一括でエクスポートし、任意の電子メールクライアントを使用して電子メールを送信できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移行について通知する方法 {#section-f3b25f672a3a4d03b0559656fd99d20a}

この移行計画を、現在のユーザに対して積極的に伝えたい場合があります。 以下に、現在のすべてのAnalyticsユーザーを送信するようにカスタマイズできるテンプレートを示します。

すべてのユーザーに電子メールを送信するには、// **[!UICONTROL Analytics]** 電子メー **[!UICONTROL Admin]** ルユー **[!UICONTROL User Management]** ザーに移 [動しま](https://marketing.adobe.com/resources/help/ja_JP/reference/t_email_users.html)す。

**件名：** Adobe Analytics と Adobe Experience Cloud へのログイン方法が新しくなります

**本文：** Adobe Analytics ユーザーの皆様へ

まもなく、すべての Adobe Analytics アカウントを [!DNL https://my.omniture.com/login/] から Adobe Experience Cloud（[experiencecloud.adobe.com](http://experiencecloud.adobe.com/)）に移行する処理を開始します。この移行により、Adobe Analyticsアカウントがアップグレードされ、Adobe Experience Cloudを介したAnalyticsへのアクセスが可能になります。 Analyticsへのアクセス方法は変更されますが、レポートスイートおよびツールに対する既存の権限はすべて保持されます。

**次のステップ：**&#x200B;ユーザーの移行は  **日付の挿入**。Analyticsアカウントの下に表示される電子メールIDにアドレスが指定された新しいログインメッセージが表示されるのを待ちます。 電子メールアドレスにリンクされた [Adobe ID](https://helpx.adobe.com/jp/x-productkb/global/adobe-id-account-change.html) (Adobe ID)を設定していない場合は、アカウントの設定を求められます。

**役立つリソース：**

[ログインとプロファイル設定の管理](https://marketing.adobe.com/resources/help/ja_JP/mcloud/getting-started-experience-cloud.html)を参照してください。

[Experience Cloudのクラウド、コアサービス](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) 、ソリューションについて

ご質問やご不明な点がある場合は、Analytics管理者にお問い合わせください。

最高の

Analytics 管理者
