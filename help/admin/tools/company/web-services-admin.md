---
description: Web Services API を使用すると、Analytics インターフェイスを通じて使用可能な機能を複製および補強するマーケティングレポートおよびその他のスイートサービスにプログラムレベルでアクセスできます。
title: Web サービス
feature: Company Settings
exl-id: d003d40e-b0b6-44f3-b9ef-ce6af61f5eb5
role: Admin
TQID: https://experienceleague.adobe.com/q0Ji-KYZJS486CKtHaDttXs3coS5hSYQd-cArPK1mCU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 42%

---

# Web サービス

Web Services API を使用すると、Analytics インターフェイスを通じて使用可能な機能を複製および補強するマーケティングレポートおよびその他のスイートサービスにプログラムレベルでアクセスできます。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]** > **[!UICONTROL 会社設定]** > **[!UICONTROL Web サービス]**&#x200B;または&#x200B;**[!UICONTROL API アクセス]**


## Analytics 2.0 API

Analytics 2.0 APIにアクセスするには、Analytics会社のグローバル会社IDが必要です。 グローバル企業IDは、[!UICONTROL API アクセス ] セクションの上部にある&#x200B;**太字**&#x200B;で確認できます。 次に例を示します。「現在ログインしているAnalytics Companyのグローバル企業IDは&#x200B;**adobe1234**&#x200B;です。」

## 従来の Web サービスを管理（非推奨）

[Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) では、権限を更新して、web サービス API へのアクセスを必要とするユーザーを含めることができます。

## WSDL：Web サービス開発者向けの web サービス API WSDL をダウンロードします

Web サービス API に関連するドキュメント、サンプルコードおよびフォーラムを提供する [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/) を参照してください。 詳しくは、「Web サービス APIの概要」をクリックします。

## フィルターオプション

SOAPを使用する際に、Web サービス API呼び出しに対する応答でXML パーサーに不正または無効な文字が発生する問題がある場合は、次のいずれかのオプションを選択して、Analyticsが応答の出力を自動的にフィルタリングします。 通常、これはダブルバイト言語（日本語、中国語、韓国語）でのみ問題になります。

## API アクセス情報

Web サービスのアクセス情報をユーザー別に表示します。 この表には、Web サービスのユーザー名と共有秘密鍵が含まれており、ユーザーはWeb サービスの呼び出しを行う際に、認証プロセスの一部として使用する必要があります。

## トークンの使用状況

現在の暦月に会社が使用したWeb サービストークンの数に関する情報を表示します。
