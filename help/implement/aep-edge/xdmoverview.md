---
title: Analytics での XDM データの使用
description: 'Adobe Analytics における Experience Platform の XDM データの使用の概要 '
translation-type: tm+mt
source-git-commit: 0a570f52c3eb62ca517770fa12f2272f6ccc978d
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 96%

---


# Analytic での Adobe Experience Platform Edge データの使用

[Adobe Experience Platform（AEP）Web SDK](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) を使用して、データを Adobe Analytics に送信できます。これを機能させるには、[Experience Data Model（XDM）](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)を Analytics で使用される形式に変換します。

Analytics は、次の 2 つの方法で XDM データを収集します。

* XDM スキーマからの自動マッピング
* コンテキストデータへの手動マッピング

## 自動マッピング

[自動マッピングは](xdm-manual.md)、XDM のデフォルトの[スキーマ](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/schema/composition.html)に依存しており、通常の Analytics データ収集に含まれる JSON オブジェクトが自動的に入力されます。XDM から設定したレポートスイートへと自動的にマッピングされる Analytic 変数には、開発者向けサポートを組み込む必要はありません。

## 手動マッピング

XDM データを Analytics に手動でマッピングする場合は、[Analytics のコンテキストデータ](../vars/page-vars/contextdata.md)変数が必要です。これらの変数は、該当するスキーマに対応する JSON オブジェクトに配置されます。通常は、開発チームが実装時にコンテキストデータを追加し、管理者が[処理ルール](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)を設定して、そのデータを指定したレポートスイートに適用します。

## セットアップ

XDMデータを受け取るようにAnalyticsを設定するには：

1. [Adobe Experience Platform Web SDK](https://docs.adobe.com/content/help/ja-JP/experience-platform/edge/fundamentals/installing-the-sdk.html) をインストールして[設定](https://docs.adobe.com/content/help/ja-JP/experience-platform/edge/fundamentals/configuring-the-sdk.html)します。

2. 該当するレポートスイートが目的のデータにマッピングされていることを確認します。XDM データは、Adobe Experience Platform から自動的にレポートスイートへ送られます。
