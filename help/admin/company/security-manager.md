---
description: レポーティングデータに対するアクセスを制御できます。オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。
solution: Analytics
title: セキュリティマネージャー
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 229ce50a24bd7b86e3859775bb4fbeba1c6a5668

---


# セキュリティマネージャー

レポーティングデータに対するアクセスを制御できます。オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。

**[!UICONTROL Analytics]** /管理者 **[!UICONTROL /カンパニー]** 設定 **[!UICONTROL /セキュリ]****[!UICONTROL ティ]**

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">堅牢なパスワードを要求</span> </td> 
   <td colname="col2">ユーザーに以下のルールに従ってより安全なパスワードを作成させます。 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">8 文字以上であること。 </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">最初と最後の文字の間に最低 1 文字の記号または数字を含むこと。 </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">最低 1 文字の英字を含むこと。 </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">辞書（英語）に載っている 1 語または複数の単語を含まないこと。 </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">ログインユーザー名にある連続した 3 文字を含まないこと。 </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">最近使用した 10 個のパスワードと異なること。 </li> 
    </ul> <p>注意：この機能は、今後新しいパスワードを設定するときに強制的に適用されるものです。既存のパスワードを確認したり、ユーザーに既存のパスワードを変更させたりすることはありません。このため、ユーザーがパスワードを変更して堅牢なパスワード規則に順守するように、     パスワードの有効期限を有効にすることを考慮してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> パスワードの有効期限</span> </td> 
   <td colname="col2"> ユーザーにアカウントパスワードを定期的に強制的に変更させます。パスワードが期限切れになる間隔を指定したり、パスワードを即座に無効にしたりできます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> IP ログイン制限の実施</span> </td> 
   <td colname="col2"> <p>(この機能は、Experience cloudログインと組み合わせて使用することはできません。 この機能は、2020年10月以降はご利用いただけません。)レポート アクセスを特定の IP アドレスまたは IP アドレスの範囲に限定します。 </p> <p>IP アドレスフィルターリストには、最大 100 個のエントリを追加でき、各エントリには特定のアドレスまたはアドレスの範囲を指定できます。 </p> <p> <span class="wintitle">IP ログイン制限の実施</span>は、「IP アドレスフィルター」リストに少なくとも 1 つのエントリが存在する状態になるまで適用されません。 </p> <p> <span class="uicontrol"> 受け入れられるIPアドレス</span>:IPアドレス範囲を指定するには、範囲を角括弧で囲みます(例： <code>
       192.168.10.[20-240]
     </code>)。 You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>失敗したログインについては<a href="/help/admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232">使用状況およびアクセスログ</a>にログが記録され、閲覧できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 電子メールドメイン制限の強制</span> </td> 
   <td colname="col2"> <p>Analytics がブックマーク、ダウンロード可能なレポートおよびアラートを送信する電子メールアドレスおよびドメインをフィルターします。 </p> <p>電子メールフィルターリストでは、最大 100 個のエントリをサポートし、各エントリは電子メールアドレスか電子メールドメイン全体を指定できます。 </p> <p>許可されていない電子メールの送信先が予定レポートに含まれる場合、Analytics は、問題の電子メール通知とレポートのスケジュールを解除するためのリンクを送信します </p> <p> <span class="wintitle">電子メールドメイン制限の強制</span>は、<span class="wintitle">許可された電子メールドメインフィルター</span>リストに少なくとも 1 つのエントリが存在するまで適用されません。 </p> <p> <span class="uicontrol"> 受け入れ済みの電子メールアドレスとドメイン</span>:IPアドレス範囲を指定するには、範囲を角括弧で囲みます(例： <code>
       192.168.10.[20-240]
     </code>)。 You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> パスワードリカバリの通知</span> </td> 
   <td colname="col2"> <p>ユーザーがユーザーアカウントのパスワードをリセットしようとすると、指定された管理者に通知します。 </p> <p> <span class="uicontrol">利用可能な管理者</span>：すべての管理者が表示されます。Ctrl キーを押しながらクリックまたは Shift キーを押しながらクリックして複数の管理者を選択できます。 </p> <p> <span class="uicontrol">電子メールメンバー</span>：現在定義済みの電子メールグループが表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## IPログイン制限の [!UICONTROL 使用終了]

「 **[!UICONTROL IPログイン制限の強制]** 」機能は、近い将来のAnalyticsの機能です。この機能を使用すると、セキュリティで保護されていると見なされる特定のIPアドレスをホワイトリストに登録し、ログインに成功し、Adobe Analytics環境にアクセスできます。 多くの場合、この機能は、ユーザがログインできる唯一のセキュアIPアドレスとして会社のIPアドレスを設定するために使用されます。 したがって、Adobe Analyticsを使用するには、ユーザーが会社のオフィスにいるか、VPN経由でネットワークにログインする必要があります。

### なぜ私たちはそれを使い終わることを考えているのか？

この機能は、Experience cloudログイン移行またはExperience cloudログインによって、状況によって機能しなくなる場合があります。 顧客属性またはオーディエンスライブラリを使用する顧客 **[!UICONTROL に対して]** 、分類する **[!UICONTROL ことが知られています]**。

また、複数のExperience cloudソリューションを所有している場合は、他のソリューションの1つを使用してExperience cloudにログインすることで、この要件を回避できます。この機能は、Analytics自体の外部では存在しないか、サポートされていません。 また、IPスプーフィングを使用してこの問題を回避することもできます。

最後に、シングルサインオンとFederated IDを使用した、機能的で優れた代替ソリューションが提供されます。 この機能により、ユーザーのログインエクスペリエンスをより詳細に制御し、セキュリティを確保できます。

### この機能を削除すると、どのように影響を受けますか。

「IPログイン制限の強制 **** 」が設定されているお客様の場合、この機能は2020年10月に削除されます。 現時点では、IPログイン制限は適用されなくなります。 それでもIPアドレスでログインを制限する必要がある場合は、シングルサインオンとFederated IDの推奨ソリューション（詳細情報とリソースは以下を参照）を確認し、実装する必要があります。

さらに、 **[!UICONTROL IPログイン制限の強制マネージャーは]** 、Analytics UIの管理者/カンパニー設定/セキュリティマネ **[!UICONTROLAージャー]** （以下を参照）から削除されます。

![](assets/sec-manager2.png)

### 他の選択肢は？

上述のとおり、このAnalytics機能は提供終了となります。 SSOおよびFederated IDの実装に時間を割くため、EOLの日付を2020年10月に延期しました。

SSO IDとFederated IDの両方が、現在導入されているIPログイン制限機能に対する優れたソリューションであり、より詳細な制御、セキュリティ、機能を提供します。

SSO/Federated IDの設定方法について詳しくは、次のヘルプドキュメントを参照してください。 アドビでは、お客様のIT部門と協力して、導入を行うことをお勧めします。

* [シングルサインオンとExperience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [管理コンソール — ID設定ドキュメント](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [管理コンソール — ID設定チュートリアル（ビデオ）](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Federated IDの設定チュートリアル（ビデオ）（英語）](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [シングルサインオン — よくある質問](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [アドビがサポートするIDタイプ](https://helpx.adobe.com/enterprise/using/identity.html)

IPログイン制限のサポートを引き続き表明し、Experience cloudによる提供をリクエストする場合は、フォーラムページでこの機能に対して投票を行うこと [ができます](https://forums.adobe.com/ideas/11648)。 SSO/Federated IDとEXCに関するその他の質問や情報については、Ryan Monger(monger@adobe.com)までお問い合わせください。
