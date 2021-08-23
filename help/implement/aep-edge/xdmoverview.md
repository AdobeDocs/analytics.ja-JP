---
title: Analytics での XDM データの使用
description: Adobe Analytics における Experience Platform の XDM データの使用の概要
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: 3def20b348713b580429e342ad3319963cae6549
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 88%

---

# Analytic での Adobe Experience Platform Edge データの使用

[Adobe Experience Platform（AEP）Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) を使用して、データを Adobe Analytics に送信できます。これを機能させるには、[Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を Analytics で使用される形式に変換します。

Analytics は、次の 2 つの方法で XDM データを収集します。

* XDM スキーマからの自動マッピング
* コンテキストデータへの手動マッピング

## 自動マッピング

自動マッピングは、XDM のデフォルトの [スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja) に依存しており、通常の Analytics データ収集に含まれる JSON オブジェクトが自動的に入力されます。XDM から設定したレポートスイートへと自動的にマッピングされる Analytic 変数には、開発者向けサポートを組み込む必要はありません。『Platform Web SDKユーザーガイド』の「 Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/automatically-mapped-vars.html)で自動的にマッピングされる変数」を参照してください。[

## 手動マッピング

[XDM データを Analytics に手動でマッピングする](xdm-manual.md)場合は、[Analytics のコンテキストデータ](../vars/page-vars/contextdata.md)変数が必要です。これらの変数は、該当するスキーマに対応する JSON オブジェクトに配置されます。通常は、開発チームが実装時にコンテキストデータを追加し、管理者が[処理ルール](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)を設定して、そのデータを指定したレポートスイートに適用します。

## セットアップ

XDM データを受信する Analytics を設定するには、次の手順を実行します。

1. [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja) をインストールして[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)します。

2. 該当するレポートスイートが目的のデータにマッピングされていることを確認します。XDM データは、Adobe Experience Platform から自動的にレポートスイートへ送られます。
