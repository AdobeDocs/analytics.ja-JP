---
description: 管理におけるレポートスイートの一般的なアカウント設定のフィールドの説明。
title: 一般的なアカウント設定
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 71%

---

# 一般的なアカウント設定

管理におけるレポートスイートの一般的なアカウント設定のフィールドの説明。

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定の編集]**／**[!UICONTROL 一般]**／**[!UICONTROL 一般的なアカウント設定]**

これらの設定には、名前やタイムゾーンなど、基本的なレポートスイート機能の編集オプションが含まれます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [&#x200B; 一般的なアカウント設定の指定 &#x200B;](https://video.tv.adobe.com/v/3411508/?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

| オプション | 説明 |
|--- |--- |
| サイトのタイトル | サイトを識別します。各レポートスイートに一意のサイトタイトルを付けます。 |
| ベース URL | レポートスイートのメインの Web サイトを指定します。ベース URL はリファラーのフィルタリングには影響しません。代わりに [&#x200B; 内部 URL フィルター &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) を使用します。 |
| タイムゾーン | レポートデータに関連付けられている日付と時刻を決定します。使用中のレポートスイートのタイムゾーンを変更すると、レポートデータに急増またはギャップが発生します。影響を最小にするため、タイムゾーンをピークでない時間帯に変更し、データの混乱を避けることをお勧めします。例えば、レポートスイートのタイムゾーンを中央から太平洋に 3:00pm で変更した場合、レポートスイートの現在の時刻は 1:00pm になります。 レポートはすでに 1:00 時間のデータを収集しているので、レポートでは 1:00pm ～ 3:00pm のトラフィックスパイクが示されます。  または、レポートスイートのタイムゾーンを中部から東部の 3:00pm に変更すると、レポートスイートの現在の時刻は 4:00pm になります。 レポートには、時間変更日の 3:00pm から 4:00pm の間のデータは表示されません。 |
| デフォルトのページ | [!UICONTROL 最頻訪問ページレポート]にページ名ではなく URL がある場合に、この設定によって同じ ページが複数の URL で表されることを防止できます。例えば、`https://example.com` と `https://example.com/index.html` という URL では、通常同じページが表示されます。デフォルトのファイル名を削除できるので、これらの URL は共に「`https://example.com`」として表示されます。空白のままにすると、URL から index.htm、index.html、index.cgi、index.asp、default.htm、default.html、default.cgi、default.asp、home.htm、home.html、home.cgi、home.asp といったファイル名が削除されます。ファイル名の削除を完全に無効にするには、URL に決して存在しない値を入力してください。 |
| IP アドレスの最後のオクテットを 0 に置き換えます | 有効にすると、IP アドレスの最後のオクテットがゼロに置き換えられます。 これは、地域関連のレポートが入力される前に発生するので、これらのレポートの精度に影響を与える可能性があります。 |
| IP の不明化 | IP アドレスを認識不可能な文字列に変更して、アドビのデータストアから削除します。IP の不明化が有効な場合、元の IP アドレスは永続的に失われます。<br> **メモ**：Data Warehouse を含め、Analytics のどこでも、IP アドレスが不明化されます。ただし、Target の IP 設定は別に制御されているので、この設定が Target に影響することはありません。<br>IP の不明化が有効な場合、必要なすべての処理（IP フィルタリング／除外、ボットルールおよび地理特性検索）は、IP アドレスが不明化される前に行われます。IP の不明化を有効にする場合、何も変更する必要はありません。<ul><li>「**無効**」をチェックすると、データの IP アドレスはそのまま変更されません。</li><li>「**IP アドレスを不明化**」をチェックすると、IP が 2 つのコロンとそれに続くハッシュ値に変更されます（例：`::1932023538`）。</li><li>「**IP アドレスを削除**」をチェックすると、地域ルックアップ後に IP アドレスがデータ内で `::X.X.X.X` に置き換えられます。</li></ul>**メモ**：この設定では、カスタム [&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) または [IP 除外 &#x200B;](/help/admin/tools/exclude-ip.md) の変更が必要になる場合があります。<br> **メモ**:Web SDKを使用して収集されたデータでは、[&#x200B; データストリーム設定 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja#@advanced-options) を通じて、Edge Networkで IP の不明化が適用される場合があります。 Analytics で IP の不明化が適用されている場合、Edge Networkに到達すると、既に不明化されています。 この不明化は、ボットルールと地域検索に影響を与えます。 |
| トランザクション ID ストレージ | [トランザクション ID](/help/import/data-sources/transactionid.md) データソースを使用できるようにします。 |
| Data Warehouse を有効化 | Analytics／ツール／Data Warehouse から Data Warehouse UI を有効にします。 |
| 郵便番号オプション | 地域 IP 検索を使用する代わりに、郵便番号を指定できます。 |
| マルチバイト文字のサポート | マルチバイト文字のサポートでは、UTF-8 を使用してレポートスイートに文字が保存されます。データを受けると、web ページの文字セットから UTF-8 文字セットにデータが変換されるので、マーケティングレポートで任意の言語を使用できるようになります。既存のレポートスイートのマルチバイト文字サポートを変更する場合は、アドビのアカウントチームまたはカスタマーケアにお問い合わせください。 |
| アクティブ化した日 | このレポートスイートがアクティブ化されているかどうかを指定します。 |
| 基準通貨 | このレポートスイートの基本[通貨](/help/implement/vars/config-vars/currencycode.md)を指定できます。 |
| 組織 ID | プロビジョニングした Experience Cloud 会社に関連付けられた ID。この ID は 24 文字の英数字から成る文字列で、その後に @AdobeOrg（必須）が続きます。 |
