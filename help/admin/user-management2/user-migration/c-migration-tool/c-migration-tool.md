---
description: Adobe Experience Cloud で Analytics ユーザー ID を Admin Console に移行するプロセスについて説明します。
seo-description: Adobe Experience Cloud で Analytics ユーザー ID を Admin Console に移行するプロセスについて説明します。
seo-title: Admin Console への Analytics ユーザーの移行
title: Admin Console への Analytics ユーザーの移行
uuid: 7d020713-693b-4945-aa52-3669a631aacb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Admin Console への Analytics ユーザーの移行{#analytics-user-migration-to-the-admin-console}

Adobe Experience Cloud で Analytics ユーザー ID を Admin Console に移行するプロセスについて説明します。

<!--
<p>FAQ <a href="https://wiki.corp.adobe.com/display/DMTM/Migration+FAQ" format="https" scope="external"> Source</a> </p>
-->

<!--
<p>Help publish link: <a href="https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/</a> </p>
<p>https://wiki.corp.adobe.com/display/analyticssolution/Migration+of+Analytics+Access+and+User+Management+to+the+Marketing+Cloud </p>
-->

このページでは、次の内容について説明します。

* [ ユーザー ID の移行とは](../c-migration-tool/c-migration-tool.md#section-adbe49aba10c4e62afa836a97894107c)
* [ユーザー ID の移行前に知っておくべき情報（FAQ）](../c-migration-tool/c-migration-tool.md#section-b0fc7f0bbd4b488e95b0c8e77ff077a9)
* [移行中に知っておくべき情報（FAQ）](../c-migration-tool/c-migration-tool.md#section-d394524aa6d046d79025bbd7499792bc)
* [移行後に知っておくべき情報（FAQ）](../c-migration-tool/c-migration-tool.md#section-9681baa01b8c41cdb9659b73b70b50ff)
* [Admin Console でサポートされない Analytics の機能](../c-migration-tool/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56)
* [移行について通知する方法](../c-migration-tool/c-migration-tool.md#section-f3b25f672a3a4d03b0559656fd99d20a)

Admin Console に関する一般的な（Analytics の移行に関連しない）ヘルプについては、『[Admin Console ユーザーガイド](https://helpx.adobe.com/enterprise/administering/user-guide.html)』を参照してください。

移行後に、Admin Console で[Experience Cloud ユーザーおよび製品を管理](https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/)できます。

## Analytics ユーザー ID の移行とは {#section-adbe49aba10c4e62afa836a97894107c}

管理者は、Analytics ユーザー ID 移行機能を使用して、Analytics User Management から Adobe Admin Console にユーザーアカウントを簡単に移行できます。移行後、ユーザーは、Adobe Experience Cloud で各ソリューションとコアサービスにアクセスすることになります。移行は、顧客ごとに段階的に実施しています。

Admin Console の使用メリットには、次のようなものがあります。

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
   <td colname="col2"> <p>Analytics ユーザーは、Adobe ID または Enterprise ID を使用して、Experience Cloud のすべてのソリューションにサインインできるようになります。このサインインにより、Experience Cloud で統合されたソリューションおよびコアサービスにアクセスできます。 </p> <p>After the migration, users who attempt to sign in via legacy logins (<span class="filepath"> my.omniture.com</span> and <span class="filepath"> sc.omniture.com</span>) are redirected to <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー ID および権限の管理 </p> </td> 
   <td colname="col2"> <p>Analytics 管理者は、<a href="http://adminconsole.adobe.com/enterprise/" format="http" scope="external">Admin Console</a>（http://adminconsole.adobe.com/enterprise/）でのみユーザーと権限を管理できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>製品およびコアサービスの管理 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">新しいユーザーの招待 </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">製品プロファイルの作成 </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">ユーザーへの特定の製品またはサービスに対する権限の付与 </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Adobe Experience Cloud で使用可能な<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html" format="html" scope="external">クロスソリューションコアサービス</a>へのアクセス権を獲得できます。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## ユーザー ID の移行前に知っておくべき情報（およびすべきこと）（FAQ）{#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

移行前に考えられる質問と、それに対する回答を示します。

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問／タスク </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Analytics 管理者として移行前の電子メールを受け取りました。最初は何をすればよいですか。 </p> </td> 
   <td colname="col2"> <p>自分が Adobe ID を持っていて、<a href="https://adminconsole.adobe.com/enterprise/" format="https" scope="external">Experience Cloud Admin Console</a> にアクセスできることを確認してください。 </p> <p>アクセスできない場合は、<a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">アドビカスタマーケア</a>に連絡してください（まず、Analytics 管理者を適切な組織に招待できるシステム管理者または製品管理者に連絡してください）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM と Analytics の統合 </p> </td> 
   <td colname="col2"> <p> Analytics との統合する AEM ユーザーは、パスワードの代わりに Analytics 共有暗号鍵を使用するよう設定を変更する必要があります。 </p> <p> この操作は、移行が有効になる前におこなう必要があります。移行が無効化されると、最初に設定されたパスワードは無効になります。 </p> <p><b>Analytics で共有暗号鍵を取得するには</b> </p> <p> 共有暗号鍵は Analytics （<span class="uicontrol">分析</span>／<span class="uicontrol">User Management</span>）から取得でき、各ユーザーで異なります。 </p> <p><b>共有暗号鍵を使用して AEM 設定を更新するには</b> </p> <p><a href="https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html" format="html" scope="external">Adobe Analytics への接続とフレームワークの作成</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Builder の更新 </p> </td> 
   <td colname="col2"> <p> <p>重要：<a href="https://marketing.adobe.com/resources/help/en_US/arb/t_install_arb.html" format="html" scope="external">Report Builder</a> のインストールを最新バージョンに更新してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行はいつ始まるのですか。 </p> </td> 
   <td colname="col2"> <p>アドビから Analytics 管理者に向けて、移行をいつ開始するかをお知らせする電子メールを送信します。 </p> <p>Admin Console への移行は段階的におこなわれます。移行当日、アドビは Analytics 管理者に通知し、移行ツールへのアクセス権を付与します。ログイン会社が移行の各段階に定義されている条件を満たしたら、アドビは以下を実施します。 </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">その会社の移行の開始日と終了日を設定します。 </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">移行の約 30 日前に、その会社の現在の Analytics 管理者に電子メール通知を送信します。 </li> 
     <li id="li_476265B24CE2404B995201170C75D674">移行の開始日を管理者に知らせる製品内通知を表示します。 </li> 
    </ul> <p> 移行当日、元の権限グループが Admin Console に自動的にコピーされます。Analytics 管理ツールで新規ユーザーを招待したり、新規グループを作成したりできなくなります。 </p> <p>移行後： </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">管理者は、Admin Console を使用して Analytics ユーザーおよび権限を管理します。（Analytics／管理者／User Management のユーザー管理インターフェイスは使用できなくなります。） </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">ユーザーは、<span class="filepath">my.omniture.com</span> ではなく、Experience Cloud から Adobe ID または Enterprise ID を使用して Analytics にアクセスするようになります。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行の開始日には何が起きますか。 </p> </td> 
   <td colname="col2"> <p>移行開始日の午前 10 時（UTC）に、以下がおこなわれます。 </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Analytics の既存の権限グループが製品プロファイルとして Admin Console に自動的に複製されます。これには、権限グループの説明や、レポートスイート、指標、ディメンション、Analytics およびレポートスイートのツールにまたがる詳細な権限が含まれます。 </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">現在の Analytics ユーザーの中に Admin Console で作成された（すなわち Adobe ID または Enterprise ID がリンクされている）ユーザーがいる場合、そのユーザーは Admin Console の適切な製品プロファイルに追加されます。 </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Analytics の「管理者」タブの「User Management」セクションは、 <span class="term"> 読み取り専用</span>. ここで新規ユーザーおよび権限グループを作成することはできなくなり、これらの機能は Admin Console で実行することになります。詳細については、<a href="../c-migration-tool/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56" format="dita" scope="local">Admin Console でサポートされない Analytics の機能</a>を参照してください。 </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">管理者は、[ユーザID移行ツール] (https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/t_migrate-users.html)へのアクセス権を付与されます。 さらに、移行の終了日（通常は 60 日後）と、ヘルプコンテンツおよび FAQ へのリンクを含む製品内通知が表示されます。 </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Admin Console の「権限」タブへのアクセス権が付与され、Analytics で従来可能であった詳細オプションをすべて持つ製品プロファイルを作成できるようになります。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー ID を移行するにはどうしたらよいですか。 </p> </td> 
   <td colname="col2"> <p> 管理者ページの「ユーザー管理」の下にある「<a href="../c-migration-tool/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9" format="dita" scope="local">ユーザー ID を移行</a>」をクリックします。ツールを使用して、ユーザーを Admin Console の製品プロファイル（Analytics の権限グループから複製したもの）に追加します。ユーザー ID の移行は自分のペースでおこなうことができます。 </p> <p>管理権限が必要です。移行が完了したら、元に戻すことはできません。 </p> <p>移行終了日になると、ログイン会社内のユーザーの <span class="filepath">my.omniture.com</span> へのアクセス権が無効になります。Users (including those that are yet to be migrated) will be redirected to login via the new Experience Cloud URL (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>注意：移行前に、ユーザーおよびグループを監査することをお勧めします。古い未使用のアカウントや、製品へのアクセス権を持つべきではなくなっているアカウント（もう組織にいない従業員など）を削除してください。 </p> <p>Related topic: <a href="../c-migration-tool/migrate-enterprise.md#topic-6fd22bc6fbc14fd69ce6a8518a5b9c00" format="dita" scope="local"> Migrate Analytics user accounts for Enterprise and Federated IDs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行は Analytics の実装やデータの収集方法に影響しますか。 </p> </td> 
   <td colname="col2"> <p>いいえ。 </p> <p>移行ツールは、ユーザー ID と権限を Analytics のユーザー管理から <a href="https://adminconsole.adobe.com/enterprise/" format="https" scope="external">Experience Cloud Admin Console</a> に移行するためのものです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行プロセスにはどれくらいかかりますか。 </p> </td> 
   <td colname="col2"> <p>現在の Analytics 管理者全員が、移行の 4 週間前に、移行前通知電子メールを受け取ります（実際の開始日は Analytics インターフェイスに表示されます）。 </p> <p>移行が始まったら、管理者は 60 日間でプロセスを完了します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行を早めることはできますか。 </p> </td> 
   <td colname="col2"> <p>はい。ただし、移行開始前に以下をおこなうことをお勧めします。 </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Admin Console で Analytics 製品管理者であることを確認する。 </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">移行が始まるとログインエクスペリエンスが変わることをユーザーベースに伝える。 </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">現在のユーザーおよび権限を監査し、クリーンアップアクティビティを実行する。 </li> 
    </ul> <p>移行を早めるには、<a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">アドビカスタマーケア</a>でカスタマーサクセスマネージャーに連絡し、開始日を早めるように依頼を送信します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Analytics 管理者ですが、Admin Console へのアクセス権がありません。Admin Console へのアクセス権を付与できるのは誰ですか。 </p> </td> 
   <td colname="col2"> <p>組織の Admin Console へのアクセス権を持つシステム管理者または製品管理者であれば、Analytics 管理者にアクセス権を付与できます。組織内で誰が Admin Console の管理者権限を持っているかわからない場合は、<a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">アドビカスタマーケア</a>にお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行開始日を延期できますか。 </p> </td> 
   <td colname="col2"> <p>はい。<a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">アドビカスタマーケア</a>に連絡してください。 </p> 
    <draft-comment> 
     <p>開始日における現在のAnalyticsユーザーおよび権限管理に対する変更については、以下を参照してください。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>会社が Admin Console への移行を予定しています。移行開始日前は、新規ユーザーおよび権限グループをどこで作成しますか。 </p> </td> 
   <td colname="col2"> <p>移行開始日前は、Admin Console または Analytics／ユーザー管理でユーザーを作成できます。 </p> <p>移行開始後は、Admin Console でのみユーザーおよび権限グループを作成できます。 </p> 
    <draft-comment> 
     <p>移行の開始日に発生する処理の詳細については、以下の「移行」の節を参照してください。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Federated ID を使用したシングルサインオンはいつ実装できるようになりますか。 </p> </td> 
   <td colname="col2"> <p> ID タイプを Adobe ID から Federated ID に変更できるツールが、まもなく Admin Console で使用可能になります。移行中に、ユーザーを Federated ID として移行することはできません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移行中に知っておくべき情報（FAQ） {#section-d394524aa6d046d79025bbd7499792bc}

移行プロセスに関する重要情報と、現在のユーザー管理に与える影響について説明します。

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>権限グループはどのように Admin Console に複製されますか。ユーザーはどうですか。 </p> </td> 
   <td colname="col2"> <p>移行された Analytics グループは、Admin Console では製品プロファイル<i></i>と呼ばれます。元のグループの権限設定は、移行時に維持されます。ただし、グループに割り当てられているユーザーは移行されません。移行ツールを使用して、そのグループに属しているユーザーを移行すると、その製品プロファイルに割り当てられます。 </p> <p>例えば、メンバーに Report Builder と Analysis Workspace（および特定のレポートスイート、指標、ディメンション）の使用権限を付与する West Coast Operations 権限グループは、West Coast Operations 製品プロファイルになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行作業を別の管理者に委任できますか。 </p> </td> 
   <td colname="col2"> <p>移行が始まったら、Experience Cloud で Analytics インスタンスにアクセスできる管理者は誰でも、移行ツールを使用してユーザーの移行を開始（または続行）できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行されていないユーザーの権限グループのメンバーシップを更新できますか。 </p> </td> 
   <td colname="col2"> <p>はい。移行されていないユーザーのグループメンバーシップは、Analytics の「ユーザー管理」セクションから変更できます。 </p> 
    <draft-comment> 
     <p>アショクの説明を待つ。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行開始後に Analytics でユーザーおよび権限グループを作成し、移行ツールを使用して Admin Console に移動することができますか。 </p> </td> 
   <td colname="col2"> <p> いいえ。移行が始まったら、すべての新規ユーザーおよび権限グループ（Admin Console では製品プロファイル）は Admin Console で作成する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行ツールを使用して移行したユーザーには、Analytics で持っていたのと同じ権限が割り当てられますか。 </p> </td> 
   <td colname="col2"> <p>はい。移行ツールを使用して移行されたユーザーには、Analytics で現在持っている権限が付与されます。さらに、Experience Cloud で Analytics にアクセスする場合は、Analytics アセット（セグメント、プロジェクト、計算指標など）へのアクセス権が維持されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console に移行されたユーザーは、引き続き <span class="filepath">my.omniture.com</span> を使用して Analytics にアクセスできますか。 </p> </td> 
   <td colname="col2"> <p>はい。移行ツールで従来のログインアクセスを無効にしない限り、移行されたユーザーは、移行終了日まで既存のユーザー名とパスワードを使用して <span class="filepath">my.omniture.com</span> で引き続き Analytics にアクセスできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Analytics レコードに同じ電子メール ID を持つユーザーが 2 人以上います。このようなユーザーを移行するとどうなりますか。 </p> </td> 
   <td colname="col2"> <p>Admin Console のユーザーアカウントには一意の電子メール ID が必要なので、このようなユーザーを複数移行しようとすると、「電子メール ID 重複」エラーが発生します。移行を再試行する前に、（従来の）「ユーザー管理」セクションで、移行されていないユーザーの電子メール ID を更新できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ユーザーの移行後は何をすればよいですか。 </p> </td> 
   <td colname="col2"> <p><span class="filepath">my.omniture.com</span> への従来のログインアクセスを無効にしてください。移行されるまで、従来のログインをオフにすることはできません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行プロセスを追跡できますか。 </p> </td> 
   <td colname="col2"> <p>移行ツールには、正常に移行されたユーザーの数と、従来のログインが無効になったユーザーの数を表示するダッシュボードが含まれています。 </p> <p> 理想的には、すべてのユーザーの移行が完了し、従来のログインが無効になると、ログイン会社の Admin Console への移行は成功します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行中に、ユーザーおよび権限の管理を実行する必要があります。このタスクを実行するには、どのツールを使用すればよいですか。 </p> </td> 
   <td colname="col2"> <p>移行開始後は、Admin Console を使用して新規ユーザーおよび製品プロファイルの作成や管理をおこないます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行ツールを使用してユーザーを移行すると、ユーザーには何が起きますか。 </p> </td> 
   <td colname="col2"> <p>Analytics ユーザーレコードの電子メール ID 宛に、Experience Cloud で Analytics にアクセスする新しい方法について知らせるウェルカムメールが届きます。既存の Adobe ID がない場合は、作成するように求められます。作成後は、その Adobe ID を使用して Analytics にアクセスできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行ツールではなく、API を使用してユーザーを移行できますか。 </p> </td> 
   <td colname="col2"> <p>いいえ。既存のユーザー全員を確実に Admin Console に移行するには、移行ツールを使用する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console で使用できない Analytics のユーザー管理機能には何がありますか。 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">アセット転送 </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">ユーザーの有効期限 </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">ユーザーログ </li> 
    </ul> <p>これらの機能は、引き続き Analytics のユーザー管理で使用できます。 </p> <p>詳細については、<a href="../c-migration-tool/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56" format="dita" scope="local">Admin Console でサポートされない Analytics の機能</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console でいくつかの設定を作成し、Analytics の権限グループにマッピングしました。移行が始まると、このような設定はどうなりますか。 </p> </td> 
   <td colname="col2"> <p>Analytics の権限グループは、その他すべてのグループと同様に、製品プロファイルとして Admin Console に再作成されます。つまり、Admin Console には、基本的に重複した権限を持つ 2 つの製品プロファイルが表示されます。重複している製品プロファイルは Admin Console から削除できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー移行後の次のステップは何ですか。 </p> </td> 
   <td colname="col2"> <p>1 人または複数のユーザーを移行したら、次のステップは <span class="filepath">my.omniture.com</span> での従来のログインを無効にすることです。これを実行するには、移行ツールでユーザーを選択し、画面上部に表示されるコンテキストオプション「従来のログインを無効化」をクリックします。このオプションは、Admin Console への移行が成功した 1 人または複数のユーザーを選択した場合にのみ表示されることに注意してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行終了日には何が起きますか。 </p> </td> 
   <td colname="col2"> <p>移行終了日（移行開始日から 60 日）の後は、ログイン会社内のすべてのユーザーが、Adobe ID を使用する Experience Cloud ログインページでのログインにリダイレクトされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移行終了日までにすべてのユーザーを移行できませんでした。移行されていないユーザーは Analytics にアクセスできなくなりますか。 </p> </td> 
   <td colname="col2"> <p>終了日までに移行されていないユーザーは、Experience cloudのログインページ(experiencecloud.adobe.com)にリダイレクトされ、Analyticsにアクセスできなくなります。 ただし、Analytics 管理者は引き続き移行ツールにアクセスできるので、ユーザーを探して移行し、アクセス権を復元することができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移行後に知っておくべき情報（FAQ） {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問／問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Admin Console からのユーザーの削除 </p> </td> 
   <td colname="col2"> <p> Analytics では、削除されたユーザーは <span class="term"> expired</span>, but the account continues to exist. アカウントを保持することで、セグメント、計算指標、スケジュールされたレポート、プロジェクトなどのアセットが転送できるようになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アカウントの有効期限 </p> </td> 
   <td colname="col2"> <p> アドミンツールの Analytics では、アカウントの有効期限を手動で設定できます。有効期限が来ると、ユーザーは Analytics にアクセスできなくなりますが、実際の Experience Cloud ユーザーアカウント（例: Adobe ID、Enterprise ID、Federated ID など）は期限切れにはなりません。これらのユーザーは引き続き Experience Cloud にログインできますが、Analytics を使用することはできなくなります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Admin Console でサポートされない Analytics の機能 {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>移行中に適用される可能性のある次の問題を確認します。

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問／問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>このユーザーとしてログイン </p> </td> 
   <td colname="col2"> <p> Admin Console への移行をおこなっている管理者は、「このユーザーとしてログイン」機能を使用して Admin Console に移行済みの管理者以外のユーザーアカウントにアクセスすることができなくなります。この機能は、Analytics で非推奨になっています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザーの有効期限とアセット転送 </p> </td> 
   <td colname="col2"> <p> Admin Console は、ユーザーの有効期限またはアセット転送をサポートしていません。管理者は、Analytics の管理ツールの「Analytics ユーザーおよびアセット」セクションを使用して、これらの機能を実行します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最終アクセス（最終ログイン） </p> </td> 
   <td colname="col2"> <p> ユーザーの最終ログイン日時に関する詳細は、Analytics ユーザーおよびアセットリンクから確認できますが、Admin Console では確認できません。Analyticsの最終ログイン日は、ユーザーがExperience cloud内から実際にAnalyticsにアクセスした日時に固有の日付で、Experience cloudにログインした日時は反映されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー管理 API の<a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">アドビがサポートしている ID タイプ</a> </p> </td> 
   <td colname="col2"> <p> Admin Console への移行をおこなっている管理者は、プログラムによって Admin Console のユーザーアカウントにアクセスできるよう、Adobe I/O で提供されている<a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html" format="html" scope="external">ユーザー管理 API</a> を設定する必要があります。 </p> <p>管理者が移行を実行できるようになると、Analytics の権限 API はオフになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web サービス資格情報 </p> </td> 
   <td colname="col2"> <p> ユーザーの Web サービス資格情報（および共有暗号鍵）は、Admin Console では使用できません。「Analytics ユーザーおよびアセット」セクションで特定のユーザーをクリックして、アクセスすることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>シングルサインオン </p> </td> 
   <td colname="col2"> <p> Analytics のシングルサインオン設定は、移行を完了すると削除されます。移行中は、これらの設定は有効なままです。Analytics のシングルサインオンを使用する顧客は、<a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">Adobe Federated ID</a> にアップグレードする必要があります。 </p> <p>Analytics では、まずユーザーを Adobe ID として移行して Experience Cloud アカウントを作成しやすくし、次にそのアカウントを統一されたシングルサインオンユーザーに変換することをお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>権限グループのダウンロード </p> </td> 
   <td colname="col2"> <p> 権限グループ情報のダウンロードは、Analytics 管理ツールおよび Adobe Admin Console のどちらでもサポートされなくなります。顧客は、adobe.io ユーザー管理 API を使用して、権限グループ情報を一括して取得する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アカウント作成日 </p> </td> 
   <td colname="col2"> <p>アカウント作成日の情報は、Analytics 管理ツールおよび Adobe Admin Console のどちらでもサポートされなくなります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>一括メール </p> </td> 
   <td colname="col2"> <p>ユーザーへの一括メールは、Analytics 管理ツールおよび Adobe Admin Console のどちらでもサポートされなくなります。顧客は、ユーザーの電子メールアドレスを Adobe Admin Console から一括して書き出し、希望する電子メールクライアントを使用してメールを送信することができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移行について通知する方法 {#section-f3b25f672a3a4d03b0559656fd99d20a}

この移行計画について、現在のユーザーにあらかじめ知らせておきたい場合は、以下のテンプレートをカスタマイズして、現在の Analytics ユーザー全員に送信することができます。

To email all users, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; [Email Users](https://marketing.adobe.com/resources/help/en_US/reference/t_email_users.html).

**件名：** Adobe Analytics と Adobe Experience Cloud へのログイン方法が新しくなります

** Body:** Adobe Analyticsユーザーの皆様へ！

Our company will begin migrating all Adobe Analytics accounts away from [!DNL https://my.omniture.com/login/] to Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). この移行に伴い、Adobe Analytics アカウントがアップグレードされ、Adobe Experience Cloud を通じて Analytics にアクセスできるようになります。Analytics にアクセスする方法は変わりますが、レポートスイートやツールに対する既存の権限はすべて維持されます。

**次の手順：**次の時点からユーザーの移行を開始します <INSERT DATE> の呼び出しの後におこなわれる場合です。ご利用の Analytics アカウントに登録されている電子メール ID 宛に、新しいログイン情報が記載されたウェルカムメッセージが送信されますので、そちらをご確認ください。[Adobe ID](https://helpx.adobe.com/x-productkb/global/adobe-id-account-change.html) を電子メールアドレスにリンクする設定をしていない場合は、アカウントを設定するように求められます。

**参考情報：**

[サインインとプロファイル設定の管理](https://marketing.adobe.com/resources/help/en_US/mcloud/getting-started-experience-cloud.html).

Experience Cloud の[クラウド、コアサービスおよびソリューションについて](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html)

質問や気になる点がありましたら、Analytics 管理者にお問い合わせください。

よろしくお願いいたします。

Analytics 管理者
