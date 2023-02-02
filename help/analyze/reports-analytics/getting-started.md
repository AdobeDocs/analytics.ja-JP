---
description: Reports & Analytics を使用する前に、Reports & Analytics の基本的なログインやタスクの設定、およびアカウント情報へのアクセス方法について理解します。
title: Reports & Analytics の概要
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 7bd8f28c-2b7a-4220-bd82-1e43edc2c0cd
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 97%

---

# Reports &amp; Analytics の基礎知識

Reports &amp; Analytics を使用する前に、Reports &amp; Analytics の基本的なログインやタスクの設定、およびアカウント情報へのアクセス方法について理解します。

>[!IMPORTANT]
>**2023 年 12 月 31 日**（PT）をもって、アドビは Reports &amp; Analytics およびそれに付随するレポートと機能を廃止する予定です。その時点で、Reports &amp; Analytics およびそのすべてのレポートとスケジュールは機能を停止します。Reports &amp; Analytics を強化するレポート、ビジュアライゼーション、基盤となる技術は、アドビの技術標準規格を満たさなくなりました。Reports &amp; Analytics のほとんどの機能は、Analysis Workspace 内で使用できます。2015年の Analysis Workspace のリリース以降、Reports &amp; Analytics の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。このお知らせでは、提供終了プロセスについて説明します。

レポートは、従来型の Web ベースのチャネルと、モバイルやビデオ、ソーシャルネットワークのような発展を続けるチャネルの両方に洞察を提供します。レポートの例には次のようなものがあります。

* サイトの訪問者数
* そのうちのユニーク訪問者数（1 回のみカウント）
* サイトへの来訪経路（リンクをたどって来訪したか、直接来訪したかなど）
* サイトのコンテンツを検索するために使用したキーワード
* 特定のページまたは全サイトでの滞在時間
* 訪問者がクリックしたリンク、およびサイトを離れた日時
* 売上高またはコンバージョンイベントを最も効果的に生み出しているマーケティングチャネル
* ビデオの視聴に費やした時間
* サイトの訪問に使用したブラウザーとデバイス

## ブラウザー要件とシステム要件

Reports &amp; Analytics インターフェイスにログインするためのブラウザーと必要システム構成を示します。

* 推奨ブラウザー：Firefox、Chrome、Safari または Edge の最新バージョン。
* cookie と JavaScript を有効にする必要があります。
* 画面の解像度 1024 x 768、画面の色 16 ビット以上。

## Reports &amp; Analytics へのログイン

インターフェイスにアクセスする前に、アカウントマネージャーまたはアドビカスタマーケアと協力して会社のアカウントを設定してください。

## Experience Cloud を使用したログイン

Adobe Experience Cloudからログインするには：

1. インターネットに接続されているコンピューターで、ブラウザーを起動します。
1. [!DNL https://login.experiencecloud.adobe.com/] にアクセスします。
1.  [!UICONTROL サインイン]ページで「**[!UICONTROL シングルサインオン]**」をクリックします。
1.  次の情報を入力し、「**[!UICONTROL サインイン]**」をクリックします。

   **[!UICONTROL 会社名]**：会社 ID（発行された半角英数字のカンパニー名）を入力します。

   **[!UICONTROL ユーザー名]**： アカウント ID を入力します。

   **[!UICONTROL パスワード]**： アカウントのパスワードを入力します。
1. Experience Cloud のホームページで、 **Analytics／レポート** に移動します。

   無操作状態が 30 分間続くと自動的に Experience Cloud からログアウトされます。

## レポートの実行

 レポートを生成するには

1. [!UICONTROL Reports &amp; Analytics] にログインします。

   レポートメニューが表示されます。設定済みの場合は、[ダッシュボード](/help/analyze/reports-analytics/dashboard.md)が表示されます。

1.  **[!UICONTROL サイトコンテンツ]**／**[!UICONTROL ページ]**（例）をクリックします。

   ![](assets/pages_report.png)

   レポートのインターフェイス機能については「[レポートの機能](/help/analyze/reports-analytics/overview/report-overview.md)」を参照してください。

## ユーザーのアカウント設定の編集

ユーザーアカウントの編集、ユーザーパスワードのリセットおよび連絡先情報の編集に関する情報を示します。

連絡先情報を表示および編集したり、パスワードを指定したり、Web サービス情報を表示したり、データ収集からこのコンピューターを除外したりすることができます。

右上のアカウント名アイコン ![](assets/account.png) をクリックし、ログイン名の横にある「**[!UICONTROL アカウントの設定]**」（車輪）をクリックします。

すべてのユーザーは、「[!UICONTROL アカウント情報]」ページにアクセスできます。次の情報を表示したり、編集したりできます。

| 情報のタイプ | 定義 |
| --- | --- |
| 連絡先 |  アカウントに次の個人情報を指定します。<ul><li>名前（必須）</li><li>姓（必須）</li><li>タイトル</li><li>電子メールアドレス（必須）</li><li>電話番号</li></ul> |
| ログイン | アカウントのユーザー名が表示され、アカウントのパスワードを変更できます。[Reports &amp; Analytics アカウントのパスワードのリセット方法](https://experienceleague.adobe.com/docs/analytics/technotes/troubleshoot-login.html) も参照してください。 |
| Web サービス | このアカウントに関連付けられた Web サービスのユーザー名と共通の秘密が表示されます。Web サービス API から Experience Cloud にアクセスする場合、これらの資格情報を使用します。詳しくは、Developer Connection を参照してください。**メモ：**&#x200B;この情報は、アカウントが Web サービスのユーザーとして認可されている場合にのみ表示されます。 |
| このコンピューターを除外 | cookie を現在のコンピューターに適用し、データ収集から除外します。これはドメイン内のページビューおよび訪問者の数がオンラインアクティビティの影響を受けないようにする場合に役立ちます。**メモ：**&#x200B;この機能を使用するには、ブラウザーで cookie が有効になっている必要があります。コンピューターから cookie を削除した場合、除外 cookie を再び設定する必要があります。 |

## インターフェイス言語の変更

インターフェイスの言語を変更できます。 選択した言語で Reports &amp; Analytics のインターフェイスを表示できます。

インターフェイス言語を変更するには：

1. Analytics にログインし、「**[!UICONTROL レポート]**」タブを選択します。
1. ページフッターで、**[!UICONTROL 言語]**&#x200B;メニューのアクティブな言語をクリックし、目的の言語を選択します。

ドキュメントおよびホームページには Adobe Experience Cloud からアクセスできます。（**[!UICONTROL ヘルプ]**／**[!UICONTROL ヘルプホーム]**&#x200B;を選択します。）

>[!NOTE]
>本製品は、北米および実際に販売されているその他の地域での販売が許可されています。 他の国や地域での販売に関する現地の要件を満たしていない場合があります。
