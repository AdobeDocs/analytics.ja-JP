---
description: Google広告とMicrosoft Advertisingのアカウント ID を見つける手順。
title: アカウント ID の見つけ方
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 586459d99674f01a3b18f84f975a3365ddf2fcd9
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 3%

---

# アカウント ID の見つけ方 {#locate-your-account-ids}

Google Ads とMicrosoft Advertisingのアカウント ID を見つける方法を説明します。

## Google広告（AdWords） {#google}

>[!IMPORTANT]
>
>Google Ads では、次の 2 種類のアカウントを使用します。
>
>- MCC （My Client Center）アカウント
>- 標準アカウント。
>
>このAdobe Analyticsとの統合には、MCC アカウントログインではなく **標準アカウントログインを使用する必要があります**。 その理由は、MCC アカウントは、1 回のログインで複数のGoogle Ads アカウントにアクセスできる「umbrella」アカウントとして機能するのに対し、Standard アカウントログインでは、1 回のログインで 1 つのアカウントにのみアクセスできるためです。 Googleは、1 つのメールを 5 つのアカウントにリンクして管理することをサポートしていますが、Advertising Analyticsはまだこの機能をサポートしていません。 1 つのメールは、1 つのGoogle Ads アカウントにのみリンクできます。

右上のアカウントアイコンをクリックして、Google Ads のアカウント番号（顧客 ID）を表示します。

![Google広告マネージャーアカウント ](assets/google-account.png)

## MicrosoftAdvertising（Bing） {#microsoft}

>[!NOTE]
>
>Microsoft Advertising（旧称 Bing）アカウントでGoogleの読み込み機能を使用している場合は、必ず正しいトラッキング文字列を更新してください。 トラッキング文字列が、Google バージョンから正しいMicrosoft Advertising トラッキング文字列に自動的に更新されず、結果として未指定のデータになる場合があります。 詳しくは、Microsoft Advertising ヘルプの [Google Ads から読み込まれる内容 ](https://help.ads.microsoft.com/apex/index/3/jp/50851/) を参照してください。

**[!UICONTROL アカウント ID]** と **[!UICONTROL マネージャーアカウント ID]** の両方が必要です。

- **[!UICONTROL アカウント ID]** は、**[!UICONTROL 設定]**/**[!UICONTROL アカウント設定]**/**[!UICONTROL アカウント ID]** にあります。 [!UICONTROL  アカウント番号 ] ではなく、[!UICONTROL  アカウント ID] を使用していることを確認してください。
- **[!UICONTROL 管理者アカウント ID]** は、**[!UICONTROL 設定]**/**[!UICONTROL 管理者アカウント設定]**/**[!UICONTROL 管理者アカウント ID]** の下にあります。 [!UICONTROL  管理者アカウント番号 ] ではなく [!UICONTROL  管理者アカウント ID] を使用していることを確認してください。

![Microsoft Advertisingのナビゲーション ](assets/bing-id.png)

>[!CONTEXTUALHELP]
>id="adanalytics_ma_account_id"
>title="アカウント ID"
>abstract="「アカウント ID」は、Microsoft Advertising インターフェイスにある数値です。 設定/アカウント設定/アカウント ID に移動すると、アカウントを見つけることができます。"

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="Manager account ID"
>abstract="「管理者アカウント ID」は、Microsoft Advertising インターフェイスにある数値です。 この場所を特定するには、設定/マネージャーアカウント設定/マネージャーアカウント ID に移動します。"
