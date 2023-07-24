---
description: Web Services API を使用すると、Analytics インターフェイスを通じて使用可能な機能を複製および補強するマーケティングレポートおよびその他のスイートサービスにプログラムレベルでアクセスできます。
title: Web サービス
feature: Company Settings
exl-id: d003d40e-b0b6-44f3-b9ef-ce6af61f5eb5
source-git-commit: d2a644d1b655153e1ad509bf9065c390d9226cfc
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 85%

---

# Web サービス

Web Services API を使用すると、Analytics インターフェイスを通じて使用可能な機能を複製および補強するマーケティングレポートおよびその他のスイートサービスにプログラムレベルでアクセスできます。

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL すべての管理者]**／**[!UICONTROL 会社の設定]**／**[!UICONTROL web サービス]** または **API アクセス**


## Analytics 2.0 API

Analytics 2.0 API にアクセスするには、Analytics 会社のグローバル会社 ID が必要です。 現在ログイン中のグローバル会社 ID を見つけることができます **太字** （この節を参照）。

## 従来の Web サービスの管理（廃止）

[Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) では、権限を更新して、web サービス API へのアクセスを必要とするユーザーを含めることができます。

## WSDL：Web サービス開発者向けの web サービス API WSDL をダウンロードします

Web サービス API に関連するドキュメント、サンプルコードおよびフォーラムを提供する [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/) を参照してください。詳しくは、「Web サービス API の概要」をクリックしてください。

## フィルターオプション

SOAP を使用しており、XML パーサーで Web Services API コールへの応答の際に不正または無効な文字による問題が発生した場合は、次のいずれかまたは両方のオプションを選択して、Analytics で応答の出力を自動的にフィルタリングするようにします。通常、これはダブルバイト文字（日本語、中国語、韓国語）でのみ発生する問題です。

## API アクセス情報

ユーザーによる Web Services へのアクセス情報を表示します。このテーブルには Web サービスのユーザー名と共有暗号鍵が含まれており、ユーザーが Web サービスをコールする際に認証処理の一部として使用する必要があります。

## トークンの使用状況

現在の月間に使用している Web サービストークン数の情報を表示します。
