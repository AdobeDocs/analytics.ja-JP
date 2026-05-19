---
description: 管理者のレポートスイートの一般アカウント設定のフィールド説明。
title: 一般的なアカウント設定
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
TQID: https://experienceleague.adobe.com/1HGpY4lstZB6baXYggrD4xni1SWbYTDLa2fqYw11yd4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 727
ht-degree: 53%

---

# 一般的なアカウント設定

管理におけるレポートスイートの一般的なアカウント設定のフィールドの説明。

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定の編集]**／**[!UICONTROL 一般]**／**[!UICONTROL 一般的なアカウント設定]**

これらの設定には、名前やタイムゾーンなど、基本的なレポートスイート機能の編集オプションが含まれます。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [一般的なアカウント設定の設定](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/manage-report-suites/configuring-general-account-settings){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

| オプション | 説明 |
|--- |--- |
| サイトのタイトル | サイトの特定： 各レポートスイートに一意のサイトタイトルを付けます。 |
| ベース URL | レポートスイートのメイン web サイトを指定します。 ベース URLは、リファラーフィルタリングには影響しません。 代わりに[内部URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)を使用してください。 |
| タイムゾーン | レポートデータに関連付けられている日付と時刻を決定します。  使用中のレポートスイートのタイムゾーンを変更すると、レポートデータに急増またはギャップが発生します。 影響を最小にするため、タイムゾーンをピークでない時間帯に変更し、データの混乱を避けることをお勧めします。  例えば、レポートスイートのタイムゾーンを中央から太平洋に3:00pmに変更すると、レポートスイートの現在の時刻は1:00pmになります。 レポートでは、1:00時間のデータが既に収集されているため、レポートでは1:00pm ～ 3:00pmの間にトラフィックが急増していることが示されます。  または、レポートスイートのタイムゾーンを中央から東部に3:00pmに変更すると、レポートスイートの現在の時間は4:00pmになります。 レポートには、時間変更日の3:00pm ～ 4:00pmの間のデータは表示されません。 |
| デフォルトのページ | [!UICONTROL 最頻訪問ページレポート]にページ名ではなく URL がある場合に、この設定によって同じ ページが複数の URL で表されることを防止できます。 例えば、`https://example.com` と `https://example.com/index.html` という URL では、通常同じページが表示されます。 デフォルトのファイル名を削除できるので、これらの URL は共に「`https://example.com`」として表示されます。  空白のままにすると、URL から index.htm、index.html、index.cgi、index.asp、default.htm、default.html、default.cgi、default.asp、home.htm、home.html、home.cgi、home.asp といったファイル名が削除されます。  ファイル名の削除を完全に無効にするには、URL に決して存在しない値を入力してください。 |
| IP アドレスの最後のオクテットを 0 に置き換えます | 有効にすると、IP アドレスの最後のオクテットが0に置き換えられます。 これは、地域に関連するレポートが入力される前に発生するため、これらのレポートの精度に影響を与える可能性があります。 |
| IP の不明化 | IP アドレスを認識できない文字列に変換し、Adobeデータストアから削除します。 IP難読化が有効になっている場合、元のIP アドレスは永続的に失われます。<br> **メモ**：Data Warehouse を含め、Analytics のどこでも、IP アドレスが不明化されます。 ただし、TargetのIP設定は個別に制御されるので、この設定はTargetには影響しません。<br> IP難読化が有効になっている場合、IP フィルタリング/除外、ボットルール、ジオセグメンテーション検索など、必要なすべての処理は、IP アドレスが難読化される前に実行されます。 IP の不明化を有効にする場合、何も変更する必要はありません。<ul><li>「**無効**」をチェックすると、データの IP アドレスはそのまま変更されません。</li><li>「**IP アドレスを不明化**」をチェックすると、IP が 2 つのコロンとそれに続くハッシュ値に変更されます（例：`::1932023538`）。</li><li>**IP アドレスの削除**&#x200B;を確認すると、地理参照の後に、IP アドレスがデータの`::X.X.X.X`に置き換えられます。<br/>このオプションは、新しいレポートスイートに対してデフォルトで選択されます。</li></ul>**メモ**：この設定では、カスタム [&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)または[IP除外](/help/admin/tools/exclude-ip.md)に変更が必要になる場合があります。<br> **注**: Web SDKを使用して収集されたデータでは、[&#x200B; データストリーム設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#@advanced-options)を通じてEdge NetworkでIP難読化を適用できます。 Edge NetworkでIP難読化が適用されている場合、Analyticsに到達したときにすでに難読化されています。 この不明化は、ルールと地理参照の両方に影響を与えます。 |
| トランザクション ID ストレージ | [トランザクション ID](/help/import/data-sources/transactionid.md) データソースを使用できるようにします。 |
| Data Warehouse を有効化 | Analytics／ツール／Data Warehouse から Data Warehouse UI を有効にします。 |
| 郵便番号オプション | 地域 IP 検索を使用する代わりに、郵便番号を指定できます。 |
| マルチバイト文字のサポート | マルチバイト文字のサポートでは、UTF-8 を使用してレポートスイートに文字が保存されます。 データを受けると、web ページの文字セットから UTF-8 文字セットにデータが変換されるので、マーケティングレポートで任意の言語を使用できるようになります。 既存のレポートスイートのマルチバイト文字サポートを変更する場合は、アドビのアカウントチームまたはカスタマーケアにお問い合わせください。 |
| アクティブ化した日 | このレポートスイートがアクティブ化されているかどうかを指定します。 |
| 基準通貨 | このレポートスイートの基本[通貨](/help/implement/vars/config-vars/currencycode.md)を指定できます。 |
| 組織 ID | プロビジョニングされたCX Enterprise会社に関連付けられているID。 この ID は 24 文字の英数字から成る文字列で、その後に @AdobeOrg（必須）が続きます。 |
