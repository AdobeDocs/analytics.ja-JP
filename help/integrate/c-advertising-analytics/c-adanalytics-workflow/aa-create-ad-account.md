---
title: Advertising Analytics で広告アカウントを設定する方法
description: 新しい広告アカウントを作成し、複数のアカウントを複数のレポートスイートにマッピングできます。
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 100%

---

# 広告アカウントの設定

Adobe Analytics Administrator は、新しい広告アカウントを作成して、複数のアカウントを複数のレポートスイート（1 対 1、1 対多、多対多）にマッピングできます。

また管理者は、Advertising アカウントを設定するための[アクセス権限を管理者以外のユーザーに付与する](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369)こともできます。

![](assets/aa_accounts.png)

1. Adobe Analytics で、**[!UICONTROL 管理者]**／**[!UICONTROL Advertising アカウント]**&#x200B;に移動します。
1. （初回の使用時のみ）エンドユーザー使用許諾契約書に同意します。
1. 「**[!UICONTROL 追加]**」をクリックします。
1. [!UICONTROL 新規検索エンジンアカウント]ダイアログが表示されます。

   ![](assets/aa_new_se_account.png)

1. 以下のガイドラインに従って「**[!UICONTROL 検索エンジンの設定]**」に入力します。

   | 設定 | 説明 |
   | --- | --- |
   | タイプ | Google AdWords と Microsoft Bing Ads の 2 つのオプションがあります。注意：Yahoo Gemini は、2019 年 3 月 31 日（PT）に Microsoft Bing に吸収されました。その結果、Yahoo Gemini 広告アカウントオプションは使用できなくなりました。 |
   | アカウント名 | このアカウント名は最適な名前に設定できます。これが UI に表示されるアカウントのわかりやすい名前になります。 |
   | OAuth のトークン | **メモ：** OAuth はアクセス委任のオープン標準です。web サイトまたはアプリケーションに他の web サイト上にある関連情報へのアクセス権限を付与しても、パスワードを渡さないようにする方法として一般的に使用されます。サードパーティの URL（efrontier.com）への誘導を示すメッセージが表示されます。アドビは efrontier を使用して、3 つのすべての検索エンジンに対して OAuth 認証プロセスを強化しています。Internet Explorer 11（またはそれ以前のバージョン）を使用している場合、3 つのどの検索エンジンでも OAuth のトークンを正しく取得できません。他の web ブラウザーを使用してください。<p>「**[!UICONTROL トークンを取得]**」をクリックすると、OAuth2 認証プロセスが開始されます。資格情報を使用して　Google／Bing 検索アカウントにサインインするように求められます。選択している検索エンジンによって、このプロセスは多少異なります。 <ul><li>Google AdWords：Google アカウント ID を入力します</li><li>Microsoft Bing：Bing アカウント ID と Bing カスタマー ID を入力します。</li></ul>これらの ID について詳しくは、これらの ID については、[アカウント ID を見つける方法](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md)を参照してください。正常にログインすると、「**[!UICONTROL OAuth のトークン]**」フィールドに「**[!UICONTROL 取得済み]**」が表示されます。 |

1. 「**[!UICONTROL トラッキング]**」セクションで、Adobe Analytics の実装による検索エンジンデータの追跡方法に関する情報を入力します。これは、検索エンジンのデータで Adobe Analytics のデータを適切に拡張するために必要な手順です。以下のガイドラインに従って「**[!UICONTROL トラッキングの設定]**」に入力します。

   | 設定 | 説明 |
   | --- | --- |
   | タイプ | <ul><li>**自動**：Advertising Cloud Engine によって、トラッキングパラメーターを検索エンジンのトラッキングテンプレート／リンク先 URL に追加する方法が決定されます。これはもっともシンプルな方法ですが、統合されたデータセットの品質が最良ではなくなる可能性があります。<br>**重要**：「自動モード」で検索エンジンのアカウントを設定するには、次の操作を実行する必要があります。<br>- 「s_kwcid」パラメータと値が、追加するアカウント内のアカウント追跡テンプレートまたはランディングページ URL に追加されます。これは、URL の最後に挿入されます。結果として、Web サーバーに特定の key=value ペアが URL の最後に必要な場合や、URL で新しい key=value ペアをサポートするための更新が必要な場合は、ご自身で追加の作業をおこなう必要がある場合があります。**注意**：このパラメーターを[コンテンツセキュリティポリシー](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html?lang=ja)に追加する必要があるかどうかを確認します。<br>-加えて、キーワードを「s_kwcid」値の一部としてランディング URL に追加できるため、特殊文字や記号が含まれている場合、Web サーバーでそれらの文字がサポートされていることを確認してください（一般的な特殊文字の例は「+」です。これは、「絞り込み部分一致」キーワードに使用されます）。</li><li>**手動**：トラッキングパラメーターを検索エンジンのトラッキングテンプレート／リンク先 URL に追加する方法を管理できます。[各検索エンジンについては手動トラッキングの例を参照してください](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md)。</li></ul> |

1. 「**[!UICONTROL マッピング]**」セクションで、この検索エンジンアカウントにリンクするレポートスイートを選択します。少なくとも 1 つのレポートスイートを指定しないと、Advertising アカウントを保存できません。複数のレポートスイートに複数のアカウントをマッピングできます（1 対 1、1 対多、多対多）。AMO で検索エンジンから取り込んだデータは、マッピングしたどのレポートスイートにもデータ分割がないようにコピーされます。

   >[!IMPORTANT]
   >
   >選択できるのは、Experience Cloud 組織にマッピングされたレポートスイートのみです。使用するレポートスイートが表示されない場合は、[Advertising Analytics のトラブルシューティング](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md)を参照してください。

   「**[!UICONTROL マッピングの設定]**」では、以下のガイドラインに従います。

   | 設定 | 説明 |
   | --- | --- |
   | レポートスイートのマッピング | レポートスイートのマッピングにより、この検索エンジンアカウントにリンクされるレポートスイートが決まります。つまり、検索エンジンデータの送信先となるレポートスイートが決まります。 |


1. 「**[!UICONTROL 保存]**」をクリックします。
1. 保存すると、免責事項に注意事項の一覧が表示されます。この注意事項を読み、理解したことを確認してください。チェックボックスを選択して、「**[!UICONTROL OK]**」をクリックします。

   Advertising Accounts [管理 UI](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) に移動し、新規に作成したアカウントが表示されます。

>[!NOTE]
>
> 検索エンジンのデータが Analytics レポートに入力され始めるまでに 24 時間以上かかることを想定する必要があります。
