---
description: GitHub の Adobe Analytics 管理 API へのリンク。
title: Adobe Analytics 1.4 API のサポート終了 FAQ
feature: Admin Tools
role: Admin
source-git-commit: 0aaeb60528f8ff1b1067f059710c9d9fa8e1886f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 1%

---

# Adobe Analytics 1.4 API のサポート終了 FAQ

## 提供終了（EOL）に関するお知らせ

**廃止されるもの**

* Adobe Analytics 1.4 API

* Adobe Analytics WSSE 認証

**いつ閉鎖されるの？**

これらのサービスは、2026 年 8 月 12 日（PT）に廃止されます。 この日付を過ぎるとアクセスできなくなります。

## 1.4 API

**これらのサービスは何ですか？**

[Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/) は、レポート、分類、データフィード、レポートスイート設定など、様々なアクションを提供する API の集まりです。

**移行するにはどうすればよいですか？**

[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) は、1.4 API ユーザーに移行パスを提供します。 現在 1.4 API を使用しているお客様は、2.0 API （Adobe Analytics アプリケーションが依存しているのと同じ API）に統合を移行して、最新の機能を活用できます。

2.0 API を使用すると、セグメントや計算指標などのコンポーネントのレポートや管理など、Analytics ユーザーインターフェイスで実行できるほぼすべてのアクションを実行できます。

**2.0 API は、1.4 API と同じ機能を提供しますか？**
1.4 API で使用できる機能は、[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) を使用して実現できます。 一部の機能は、1.4 API で使用できる機能と同じ機能を提供し、セグメントや計算指標などのコンポーネントのレポートや管理など、Analytics ユーザーインターフェイスで実行できるほぼすべてのアクションを実行できます。

## WSSE 認証

**これらのサービスは何ですか？**

WSSE 認証は、Analytics 1.4 API でサポートされるレガシー認証プロトコルです。 これは、[Adobe Developer Console](https://developer.adobe.com/console/home) で提供される OAuth ベースの認証オプションに置き換えられました。

**移行するにはどうすればよいですか？**

WSSE のお客様は、Adobe Developer Consoleでプロビジョニングされた資格情報を使用するように認証を更新する必要があります。 これを行うには、[Adobe Developer Console](https://developer.adobe.com/console/home) にログインして、Analytics 2.0 API 統合用のプロジェクトを作成します。 OAuth ユーザー認証方法と OAuth サーバー間認証方法の中から選択します。

## 質問

Q:**これは、Analytics API の既存のAdobe I/O プロジェクトに影響しますか？**

回答：Analytics 1.4 API を使用している既存のプロジェクトが影響を受けます。 これらの統合は、EOL 期日の前に [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があります。

Q:**Adobe資格情報を、Analytics API を使用する別の製品またはアプリケーションと共有しました。 影響の有無**

回答：その製品またはアプリケーションが WSSE 資格情報を使用したり、Analytics 1.4 API を呼び出したりすると、影響を受け、EOL 期限の前に移行する必要があります。 移行プランと移行スケジュールについて詳しくは、製品またはアプリケーションのプロバイダーにお問い合わせください。

Q:**使用しているAdobe Analytics API が不明です。**

A：統合で呼び出されるアドレスによって、使用している API を識別できます。

Adobe Analytics 1.4 API にアクセスするには、次のいずれかの URL を呼び出します。
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) にアクセスするには、次の URL を呼び出します。
* https://analytics.adobe.io

API*.omniture.comを使用している場合は、[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があります。

Q:Adobe Analytics 2.0 API は **1.4 API と同一ですか？ そうでない場合、最大の違いは何ですか？**

回答：Adobe Analytics 2.0 API は 1.4 API と同一ではありませんが、次の利点など、同等の機能を提供します。

* よりシンプルで効率的なクエリ方法により、応答時間が短縮され、ポーリングが不要になります

* クエリと動的レポートの更新をプログラムで行う機能

* エラー処理の精度が向上

* Analysis Workspaceで実行できるすべての処理を実行する柔軟な機能

* UI アクションに対する API 呼び出しの一貫性と一致

* Analysis Workspaceで使用されるすべてのAttribution IQモデルへのアクセス

* Analysis Workspaceで使用されるすべての異常値検出アルゴリズムへのアクセス

* 他のExperience Cloudとの統合機能

* 複数の分類レポートの容量の増加

* 最新の Analytics 機能にアクセスする

この [Adobe Analytics 2.0 API への移行 ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) ガイドでは、1.4 API と 2.0 API の主な違いについて説明しています。 追加情報は、[Analytics 2.0 API FAQ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/) でも参照できます。

Q:**これはデータ収集に影響しますか？**

回答：Adobe Analytics 1.4 の EOL は、タグ付けソリューション（タグ（以前のAdobe Launch）、WebSDK、AppMeasurement.js など）には影響しません。 ただし、1.4 Data Sources API、Data Insertion API、Classifications API を使用してデータを収集または強化する場合は、それらのワークフローをAdobe Analytics 2.0 API に移行する必要があります。 詳しくは、[2.0 API エンドポイントガイドを参照 ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/) てください。

Q:**この FAQ で質問に答えられなかった場合はどうすればよいですか？**

A：まだ質問がある場合は、Adobeアカウント担当者にお問い合わせください。

