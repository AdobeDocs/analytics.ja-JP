---
description: レポーティングデータに対するアクセスを制御できます。オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。
solution: Analytics
title: セキュリティマネージャー
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# セキュリティマネージャー

セキュリティマネージャを使用すると、レポートデータへのアクセスを制御できます。 オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。

## 設定

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
   <td colname="col2"> <p>(この機能は、Experience cloudログインと組み合わせて使用することはできません。 この機能は、2020年10月以降はご利用いただけません。 [詳細…](/help/admin/company/login-restrictions-eol.md)レポートのアクセスを特定のIPアドレスまたはIPアドレス範囲に制限します。 </p> <p>IP アドレスフィルターリストには、最大 100 個のエントリを追加でき、各エントリには特定のアドレスまたはアドレスの範囲を指定できます。 </p> <p> <span class="wintitle">IP ログイン制限の実施</span>は、「IP アドレスフィルター」リストに少なくとも 1 つのエントリが存在する状態になるまで適用されません。 </p> <p> <span class="uicontrol"> 受け入れられるIPアドレス</span>:IPアドレス範囲を指定するには、範囲を角括弧で囲みます(例： <code>
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

| 要素 | 説明 |
|--- |--- |
| 堅牢なパスワードを要求 | ユーザーに以下のルールに従ってより安全なパスワードを作成させます。 <ul><li>8 文字以上であること。</li><li>最初と最後の文字の間に少なくとも1文字の記号または数字を含める必要があります。</li><li>最低1文字の英字が必要です。</li><li>辞書（英語）に載っている 1 語または複数の単語を含まないこと。</li><li>ログインユーザー名にある連続した 3 文字を含まないこと。</li><li>最近使用した 10 個のパスワードと異なること。</li></ul>**注意**:この機能は、今後新しいパスワードに対して適用されます。 既存のパスワードを確認したり、ユーザーに既存のパスワードを変更させたりすることはありません。このため、ユーザーがパスワードを変更して堅牢なパスワード規則に順守するように、     パスワードの有効期限を有効にすることを考慮してください。 |
| パスワードの有効期限 | ユーザーにアカウントパスワードを定期的に強制的に変更させます。パスワードが期限切れになる間隔を指定したり、パスワードを即座に無効にしたりできます。 |
| IP ログイン制限の実施 | (この機能は、Experience cloudログインと組み合わせて使用することはできません。 この機能は、2020年10月以降はご利用いただけません。 [その他](/help/admin/company/login-restrictions-eol.md)<br> )レポートのアクセスを特定のIPアドレスまたはIPアドレス範囲に制限します。 IP アドレスフィルターリストには、最大 100 個のエントリを追加でき、各エントリには特定のアドレスまたはアドレスの範囲を指定できます。IP ログイン制限の実施は、「IP アドレスフィルター」リストに少なくとも 1 つのエントリが存在する状態になるまで適用されません。Accepted IP Address: To specify an IP address range, enclose the range in brackets (for example, `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*8) Failed logins are logged and viewable from the [Usage and Access Log](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| 電子メールドメイン制限の強制 | Analytics がブックマーク、ダウンロード可能なレポートおよびアラートを送信する電子メールアドレスおよびドメインをフィルターします。電子メールフィルターリストでは、最大 100 個のエントリをサポートし、各エントリは電子メールアドレスか電子メールドメイン全体を指定できます。許可されていない電子メールの送信先が予定レポートに含まれる場合、Analytics は、問題の電子メール通知とレポートのスケジュールを解除するためのリンクを送信します&#x200B;**[!UICONTROL 電子メールドメイン制限の強制]**&#x200B;は、許可された電子メールドメインフィルターリストに少なくとも 1 つのエントリが存在するまで適用されません。**[!UICONTROL 受け入れ済みの電子メールアドレスとドメイン]**:IPアドレス範囲を指定するには、範囲を角括弧で囲みます(例：192.168.10.[20-240])。 You can also use wildcards to specify any number from 0 to 255 (for example, 192.168.[10-14].*) |
| パスワードリカバリの通知 | ユーザーがユーザーアカウントのパスワードをリセットしようとすると、指定された管理者に通知します。**[!UICONTROL 利用可能な管理者]**：すべての管理者が表示されます。Ctrl キーを押しながらクリックまたは Shift キーを押しながらクリックして複数の管理者を選択できます。**[!UICONTROL 電子メールメンバー]**：現在定義済みの電子メールグループが表示されます。 |
