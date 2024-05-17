---
title: Advertising Analytics で広告アカウントを設定する方法
description: この記事では、新しい広告アカウントを作成し、複数のアカウントを複数のレポートスイートにマッピングする方法について説明します。
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: a34dfc63c47b6fe4b91b2b67ea21cdddafb0bfd0
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 31%

---

# 広告アカウントの設定

Adobe Analytics管理者は、新しい広告アカウントを作成し、複数のアカウントを複数のレポートスイート（1 : 1、1：多数、多数）にマッピングできます。

また管理者は、Advertising アカウントを設定するための[アクセス権限を管理者以外のユーザーに付与する](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369)こともできます。

<!--
![](assets/aa_accounts.png)
-->

1. Adobe Analytics で、**[!UICONTROL 管理者]**／**[!UICONTROL Advertising アカウント]**&#x200B;に移動します。
1. （初回の使用時のみ）エンドユーザー使用許諾契約書に同意します。
1. を選択 **[!UICONTROL +追加]**.
1. この [!UICONTROL 新しい検索エンジン設定] ダイアログが表示されます。

   ![](assets/aa-new-se-account.png)

1. を入力します **[!UICONTROL 検索エンジン設定]** 次のガイドラインに従います。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL タイプ]** | 次の 2 つのオプションがあります。 **[!UICONTROL Google Adwords]** および **[!UICONTROL Bing Ads]**.  注意：Yahoo Gemini は、2019 年 3 月 31 日（PT）に Microsoft Bing に吸収されました。その結果、Yahoo Gemini 広告アカウントオプションは使用できなくなりました。 |
   | アカウント名 | このアカウント名は、自分に合った任意の名前に設定できます。  アカウント名は、UI に表示されるアカウントのわかりやすい名前です。 |
   | OAuth のトークン | **注意**:OAuth はアクセス委任のオープン標準です。web サイトまたはアプリケーションに web サイト上の情報へのアクセス権限を付与しても、パスワードを提供しないという方法として一般的に使用されます。 サードパーティの URL （efrontier.com）にルーティングされていることがわかります。 Adobeは、Adobe Media Optimizerを使用して、3 つのすべての検索エンジンに対して OAuth 認証プロセスを強化します。 Internet Explorer 11 （またはそれ以前のバージョン）を使用している場合、3 つのどの検索エンジンでも OAuth トークンを取得できません。 他の web ブラウザーを使用してください。<p>を選択 **[!UICONTROL トークンの取得]** OAuth2 認証プロセスを起動します。 資格情報を使用してGoogle/Bing 検索アカウントにログインするように求められます。 どちらを選択したかによって、このプロセスは少し異なります。 <ul><li>Google AdWords：Google アカウント ID を入力します</li><li>Microsoft Bing：Bing アカウント ID と Bing カスタマー ID を入力します。</li></ul>こちらを参照してください [アカウント ID を見つける](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) これらの ID について詳しくは、を参照してください。 正常にログインすると、「**[!UICONTROL OAuth のトークン]**」フィールドに「**[!UICONTROL 取得済み]**」が表示されます。 |

1. が含まれる **[!UICONTROL トラッキング]** Adobe Analyticsの実装を使用してデータをトラッキングする方法について説明します。 トラッキングは、Adobe Analytics データを検索エンジンデータで適切に拡張するために必要な手順です。
以下のガイドラインに従って「**[!UICONTROL トラッキングの設定]**」に入力します。

   | 設定 | 説明 |
   | --- | --- |
   | タイプ | <ul><li>**自動**：トラッキングパラメーターをのトラッキングテンプレート/出力先 URL に追加する方法をAdvertising Cloud エンジンで決定できます。 [!UICONTROL 自動タイプトラッキング] は最も単純なアプローチですが、最適な統合データセットにならない場合があります。<br>**重要：** で検索エンジン アカウントを設定するには [!UICONTROL 自動タイプトラッキング]は、次のアクションを実行する責任があります。<ul><li>この `s_kwcid` パラメーターと値が、追加するアカウントのアカウントトラッキングテンプレートまたはランディングページ URL に追加されます。 パラメーターと値が URL の末尾に挿入されます。 Web サーバーで特定の権限が必要な場合は、追加のアクションが必要になる場合があります `key=value` URL の末尾にをペアにします。 または、新規サポートの更新 `key=value` url のペアが必要です。 **注意**：このパラメーターをに追加する必要があるかどうかについて詳しく説明します [コンテンツセキュリティポリシー](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).</li><li>加えて、キーワードを `s_kwcid` 値の一部としてランディング URL に追加できます。キーワードに特殊文字や記号が含まれる場合は、使用している Web サーバーがこれらの文字をサポートできるかどうかを確認してください。 一般的な特殊文字の例を以下に示します `+`（「部分一致で変更」のキーワードで使用されます）</li></ul></li><li>**手動**：検索エンジンのトラッキングテンプレート/宛先 URL にトラッキングパラメーターを追加する方法を管理できます。 [各検索エンジンについては手動トラッキングの例を参照してください](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md)。</li></ul> |

1. が含まれる **[!UICONTROL マッピング]** この検索エンジンアカウントにリンクするレポートスイートを 1 つ以上選択します。 少なくとも 1 つのレポートスイートを指定しないと、Advertising アカウントを保存できません。複数のアカウントを複数のレポートスイート（1 : 1、1：多数、多数）にマッピングできます。 Adobe Media Optimizerが検索エンジンから取り込むデータは、マッピングされたレポートスイートに単にコピーされるので、データを分割することはできません。

   >[!IMPORTANT]
   >
   >選択できるのは、Experience Cloud 組織にマッピングされたレポートスイートのみです。使用するレポートスイートが表示されない場合は、[Advertising Analytics のトラブルシューティング](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md)を参照してください。

   「**[!UICONTROL マッピングの設定]**」では、以下のガイドラインに従います。

   | 設定 | 説明 |
   | --- | --- |
   | レポートスイートのマッピング | レポートスイートのマッピングにより、この検索エンジンアカウントにリンクされるレポートスイートが決まります。つまり、検索エンジンデータの送信先となるレポートスイートが決まります。 |


1. 「**[!UICONTROL 保存]**」を選択します。
1. 免責事項には、注意事項のリストが表示されます。 読み終えたことを確認し、この契約書を理解します。 チェックボックスを選択し、 **[!UICONTROL OK]**.

   Advertising Accounts [管理 UI](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) に移動し、新規に作成したアカウントが表示されます。

>[!NOTE]
>
>検索エンジンデータが Analytics レポートへの入力を開始するまで、少なくとも 24 時間待つことをお勧めします。
