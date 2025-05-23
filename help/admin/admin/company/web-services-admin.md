---
description: Web Services API を使用すると、Analytics インターフェイスを通じて使用可能な機能を複製および補強するマーケティングレポートおよびその他のスイートサービスにプログラムレベルでアクセスできます。
title: Web サービス
feature: Company Settings
exl-id: d003d40e-b0b6-44f3-b9ef-ce6af61f5eb5
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 75%

---

# Web サービス

Web Services API を使用すると、Analytics インターフェイスを通じて使用可能な機能を複製および補強するマーケティングレポートおよびその他のスイートサービスにプログラムレベルでアクセスできます。

**[!UICONTROL Analytics]**/**[!UICONTROL 管理者]**/**[!UICONTROL すべての管理者]**/**[!UICONTROL 会社設定]**/**[!UICONTROL Web サービス]** または **[!UICONTROL API アクセス]**


## Analytics 2.0 API

Analytics 2.0 API にアクセスするには、Analytics 会社のグローバル会社 ID が必要です。 「[!UICONTROL API アクセス &#x200B;]」セクションの上部にある **太字** にグローバル会社 ID を確認できます。 次に例を示します。「現在ログインしている Analytics Company のグローバル会社 ID は **adobe1234** です。」

## 従来の Web サービスの管理（非推奨）

[Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) では、権限を更新して、web サービス API へのアクセスを必要とするユーザーを含めることができます。

## WSDL：Web サービス開発者向けの web サービス API WSDL をダウンロードします

Web サービス API に関連するドキュメント、サンプルコードおよびフォーラムを提供する [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/) を参照してください。詳しくは、「Web サービス API の概要」をクリックしてください。

## フィルターオプション

SOAP を使用しており、XML パーサーで Web Services API コールへの応答の際に不正または無効な文字による問題が発生した場合は、次のいずれかまたは両方のオプションを選択して、Analytics で応答の出力を自動的にフィルタリングするようにします。通常、これはダブルバイト文字（日本語、中国語、韓国語）でのみ発生する問題です。

## API アクセス情報

ユーザーによる Web Services へのアクセス情報を表示します。このテーブルには Web サービスのユーザー名と共有暗号鍵が含まれており、ユーザーが Web サービスをコールする際に認証処理の一部として使用する必要があります。

## トークンの使用状況

現在の月間に使用している Web サービストークン数の情報を表示します。
