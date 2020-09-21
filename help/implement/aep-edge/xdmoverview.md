---
title: Analytics での XDM データの使用
description: 'Adobe Analytics における Experience Platform の XDM データの使用の概要 '
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

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

XDM データを受信する Analytics を設定するには、次の手順を実行します。

1. [Adobe Experience Platform Web SDK](https://docs.adobe.com/content/help/ja-JP/experience-platform/edge/fundamentals/installing-the-sdk.html) をインストールして[設定](https://docs.adobe.com/content/help/ja-JP/experience-platform/edge/fundamentals/configuring-the-sdk.html)します。

2. 該当するレポートスイートが目的のデータにマッピングされていることを確認します。XDM データは、Adobe Experience Platform から自動的にレポートスイートへ送られます。
