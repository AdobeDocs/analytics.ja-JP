---
description: Google AdsおよびMicrosoft Advertisingのアカウント IDの確認に役立つ手順。
title: アカウント ID の見つけ方
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 586459d99674f01a3b18f84f975a3365ddf2fcd9
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 20%

---

# アカウント ID の見つけ方 {#locate-your-account-ids}

Google AdsおよびMicrosoft Advertisingのアカウント IDを見つける方法について説明します。

## Google広告（AdWords） {#google}

>[!IMPORTANT]
>
>Google Adsでは、次の2種類のアカウントを使用します。
>
>- MCC （My Client Center） アカウント
>- 標準アカウント：
>
>Adobe Analyticsとの統合を行うには、MCC アカウントのログインではなく、標準アカウントのログイン **を使用する必要があります。** その理由は、MCC アカウントが1回のログインで複数のGoogle Ads アカウントにアクセスできる「傘」アカウントとして機能するのに対し、Standard アカウントのログインでは、1回のログインにつき1つのアカウントにしかアクセスできないためです。 Googleでは、1つの電子メールを5つのアカウントにリンクすることはサポートされていますが、Advertising Analyticsではまだこの機能をサポートしていません。 1つのメールは、1つのGoogle Ads アカウントにのみリンクできます。

右上のアカウントアイコンをクリックして、Google Adsのアカウント番号（お客様ID）を表示します。

![Google Ads Manager アカウント ](assets/google-account.png)

## Microsoft 広告（Bing） {#microsoft}

>[!NOTE]
>
>Microsoft Advertising（旧Bing）アカウントでGoogleの読み込み機能を使用している場合は、必ず正しいトラッキング文字列を更新してください。 トラッキング文字列は、Google バージョンから正しいMicrosoft Advertising トラッキング文字列に自動的に更新されないため、データが不特定になる可能性があります。 詳しくは、Microsoft Advertising ヘルプの[Google Adsから読み込まれるもの](https://help.ads.microsoft.com/apex/index/3/jp/50851/)を参照してください。

**[!UICONTROL アカウント ID]**&#x200B;と&#x200B;**[!UICONTROL マネージャーのアカウント ID]**&#x200B;はどちらも必要です。

- **[!UICONTROL アカウント ID]**&#x200B;は、**[!UICONTROL 設定]** > **[!UICONTROL アカウント設定]** > **[!UICONTROL アカウント ID]**&#x200B;の下にあります。 [!UICONTROL  アカウント番号]ではなく、[!UICONTROL  アカウント ID]を使用していることを確認してください。
- **[!UICONTROL マネージャーアカウント ID]**&#x200B;は、**[!UICONTROL 設定]** > **[!UICONTROL マネージャーアカウント設定]** > **[!UICONTROL マネージャーアカウント ID]**&#x200B;の下にあります。 [!UICONTROL  マネージャーアカウント番号]ではなく、[!UICONTROL  マネージャーアカウント ID]を使用していることを確認してください。

![Microsoft Advertising ナビゲーション ](assets/bing-id.png)

>[!CONTEXTUALHELP]
>id="adanalytics_ma_account_id"
>title="アカウント ID"
>abstract="「アカウント ID」は、Microsoft 広告インターフェイスにある数値です。設定／アカウント設定／アカウント ID に移動すると、アカウントを見つけることができます。"

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="マネージャーアカウント ID"
>abstract="「マネージャーアカウント ID」は、Microsoft 広告インターフェイスにある数値です。設定／マネージャーアカウント設定／マネージャーアカウント ID に移動すると、アカウントを見つけることができます。"
