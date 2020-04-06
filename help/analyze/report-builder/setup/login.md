---
description: Report Builder への 3 種類のログイン方法に関する情報です。
title: Report Builder へのログイン
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Report Builder へのログイン

Report Builder への 3 種類のログイン方法に関する情報です。

Currently, the following login options are available when you click **[!UICONTROL Sign In]** to Report Builder.

![](assets/login_screen.png)

* [標準 ](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [シングルサインオン ](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)
* [Experience Cloud とシングルサインオン ](/help/analyze/report-builder/setup/login.md#section_1FA230F35AB54021A874A7A28DE4C850)

## 標準 {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Adobe Analytics の資格情報を使用して Report Builder にログインする場合は、このログインを使用します。

**Report Builder ログイン - フィールド定義**

| フィールド | 定義 |
|--- |--- |
| 会社名 | Adobe Analyticsで使用する会社ログイン資格情報。 |
| ユーザー名 | Adobe Analyticsで使用するユーザー名。 ユーザーに対してスケジュールされたタスクは、ユーザー名にリンクされます。 同じログイン表示でreport builderにログインすると、スケジュール済みのタスクを任意のコンピューターからログインできます。 |
| パスワード | Analyticsのパスワード。 |
| このアカウントを記憶する | ログイン情報は暗号化され、Report Builderがインストールされているコンピューター上のプロファイルファイルに保存されます。 ログイン情報が保存されるので、レポートの作成者と同じ PC を使用してレポートを含むスプレッドシートを開く場合は誰でもデータの更新と編集ができます。他のユーザーとコンピューターを共有している場合に、スプレッドシートのデータが他のユーザーによって更新されるのを防ぐには、このオプションを無効にしておいてください。自動ログイン設定を無効にするには、ツールバーの **[!UICONTROL Log in With Different Credentials]** をクリックし、無効にしま **[!UICONTROL Remember Me]**&#x200B;す。 |
| プロキシサーバーの使用 | プロキシサーバーを介してインターネットにアクセスし、プロキシのユーザー名とパスワードを入力する必要がある場合に有効にします。 |

## シングルサインオン {#section_6970A5F926774976B85FFE576610E85F}

この（従来の）シングルサインオンは、Adobe Analyticsにのみログインし、Experience Cloud全体にはログインしません。

また、ドメインを入力すると、そのドメインをシステムが認識し、会社のログインページにリダイレクトされて Adobe Analytics へのログインが可能になります。

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

Experience Cloudログインを使用すると、Enterprise ID（電子メールアドレスとパスワード）を使用してAdobe Experience Cloudにログインできます。 >をクリッ **[!UICONTROL Sign In]** クし **[!UICONTROL Sign in with an Enterprise ID]** て、会社のシングルサインオンページにリダイレクトされます。 Enterprise IDの詳細については、ここをクリックしてく [ださい](https://helpx.adobe.com/jp/enterprise/kb/enterprise-id-faq.html#whatis)。

![](assets/adobe_id_login.png)

>[!NOTE]Experience Cloud ログインはセッションベースであり、トークンは 30 日後に期限切れになります。

