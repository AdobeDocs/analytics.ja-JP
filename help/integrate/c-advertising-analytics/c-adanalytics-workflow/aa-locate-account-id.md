---
description: ここでは Google や Bing のアカウント ID を簡単に見つけるための手順を説明しています。
title: アカウント ID の見つけ方
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 67%

---

# アカウント ID の見つけ方

ここでは Google や Bing のアカウント ID を簡単に見つけるための手順を説明しています。

## Google AdWords {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords では、次の 2 種類のアカウントを使用します。
>
>- MCC （My Client Center）アカウント
>- 標準アカウント。
>
>このAdobe Analyticsとの統合には、MCC アカウントログインではなく **標準アカウントログインを使用する必要があります**。 これは、MCC アカウントはシングルログインで複数の AdWords アカウントにアクセスできる「umbrella」アカウントとして機能するのに対し、Standard アカウントログインではログインごとに 1 つの AdWords アカウントのみにアクセスできるためです。Google は 1 つの電子メールをリンクして 5 つのアカウントを管理することをサポートしていますが、Advertising Analytics はまだこの機能をサポートしていません。 1 つの電子メールは 1 つの Adwords アカウントにのみリンクさせることができます。

AdWords アカウント番号（顧客 ID）を表示するには、右上のアカウントアイコンをクリックします。

![](assets/google_account.png)

## Bing {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Bing アカウントでGoogleの読み込み機能を使用している場合は、必ず正しいトラッキング文字列を更新してください。 トラッキング文字列が、Google バージョンから正しい Bing トラッキング文字列に自動的に更新されず、結果として未指定のデータになる場合があります。 この機能の詳細については、[こちら](https://help.ads.microsoft.com/apex/index/3/jp/50851/)をご覧ください。

アカウント ID と顧客 ID の両方が必要です。これらは「アカウント」タブに表示されます。

>[!NOTE]
>
>アカウント番号はアカウント ID は異なります。

![](assets/bing_id.png)
