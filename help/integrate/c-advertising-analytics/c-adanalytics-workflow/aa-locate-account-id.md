---
description: ここでは Google や Bing のアカウント ID を簡単に見つけるための手順を説明しています。
title: アカウント ID の見つけ方
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 0453f374e9027d1c539682212e880c4ebc81152f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 55%

---

# アカウント ID の見つけ方

ここでは Google や Bing のアカウント ID を簡単に見つけるための手順を説明しています。

## Google広告（AdWords） {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords では、次の 2 種類のアカウントを使用します。
>
>- MCC （My Client Center）アカウント
>- 標準アカウント。
>
>このAdobe Analyticsとの統合には、MCC アカウントログインではなく **標準アカウントログインを使用する必要があります**。 これは、MCC アカウントはシングルログインで複数の AdWords アカウントにアクセスできる「umbrella」アカウントとして機能するのに対し、Standard アカウントログインではログインごとに 1 つの AdWords アカウントのみにアクセスできるためです。Google は 1 つの電子メールをリンクして 5 つのアカウントを管理することをサポートしていますが、Advertising Analytics はまだこの機能をサポートしていません。 1 つの電子メールは 1 つの Adwords アカウントにのみリンクさせることができます。

AdWords アカウント番号（顧客 ID）を表示するには、右上のアカウントアイコンをクリックします。

![Google広告マネージャーアカウント ](assets/google-account.png)

## MicrosoftAdvertising（Bing） {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Microsoft Advertising（旧称 Bing）アカウントでGoogleの読み込み機能を使用している場合は、必ず正しいトラッキング文字列を更新してください。 トラッキング文字列が、Google バージョンから正しい Bing トラッキング文字列に自動的に更新されず、結果として未指定のデータになる場合があります。 この機能の詳細については、[こちら](https://help.ads.microsoft.com/apex/index/3/jp/50851/)をご覧ください。

**[!UICONTROL アカウント ID]** と **[!UICONTROL アカウント番号]** の両方が必要です。 これらは、「設定 **[!UICONTROL 内の「**[!UICONTROL  アカウント設定 ]**」タブに一覧表示さ]** ます。

>[!NOTE]
>
>アカウント番号はアカウント ID は異なります。

![MicrosoftAdvertising](assets/bing-id.png)
