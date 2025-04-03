---
description: Analytics インベントリの使用
title: Analytics インベントリ
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: fceb28b7af480e6d87abf09c26f45a7afb2d3270
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 36%

---

# Analytics インベントリ {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Analytics インベントリ"
>abstract="このページでは、プロジェクトとコンポーネントの数、レポートスイート、ユーザーなど、Adobe Analytics 環境の包括的な概要について説明します。この情報は、Customer Journey Analytics へのアップグレードの準備を開始する際に特に役立ちます。"

<!-- markdownlint-enable MD034 -->

Analytics Inventory は、プロジェクトとコンポーネントの数、レポートスイート、ユーザーなど、Adobe Analytics環境の包括的な概要を提供します。 この情報は、Customer Journey Analytics へのアップグレードの準備を開始する際に特に役立ちます。

このアプリケーションの目標は、次の質問に答えるのに役立つことです。

* 組織にとって、アップグレードが必要なアセット（レポートスイート、セグメント、ユーザー、ワークスペースプロジェクト、データフィードなど）や残すことができるアセットはどれですか？

* 移行する必要があるアセットを決定したら、次の手順を実行します。

   * このアップグレードの前にアセットのクリーンアップを実行する必要がありますか。

   * プロセスの一環としてアセットの統合を行う必要がありますか？

   * アップグレードシーケンスはアセットに対して何にする必要がありますか？

   * 最初にアップグレードする必要があるレポートスイートのグループは何ですか？ 最後？

## 権限

Analytics Inventory は、[Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics) のAdobe Analytics製品管理者権限を持つユーザーが使用できます。

## Analytics インベントリへのアクセス

1. **[!UICONTROL 管理者]** メニューの **[!UICONTROL Analytics インベントリ]** をクリックします。 または、**[!UICONTROL すべての管理者]**/**[!UICONTROL Analytics インベントリ]** に移動します。

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. メイン画面には、Adobe Analytics環境の包括的なインベントリが表示されます。

   ![ メインインベントリ画面 ](assets/an_inventory.png)

>[!IMPORTANT]
>
>   この最初のリリースでは、Workspace プロジェクト、セグメント、計算指標、詳細（Media Analytics）データおよびユーザーの概要数値を確認できます。 現在、アクションにつながる項目はレポートスイートのみです。


## コンポーネント {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="コンポーネント"
>abstract="このセクションには、Adobe Analytics 環境に存在するプロジェクト、セグメント、計算指標の数が表示されます。プロジェクトとコンポーネントは、Customer Journey Analytics に移行できます。"

<!-- markdownlint-enable MD034 -->

この最初のリリースでは、Workspace プロジェクト、セグメントおよび計算指標の概要在庫数を確認できます。 今後のリリースでは、これらのコンポーネントを分析できるようになります。

## データの設定と収集 {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="データの設定と収集"
>abstract="このセクションには、Adobe Analytics 環境内のレポートスイートの数と、ストリーミングメディアへのアクセス権が表示されます。 "

<!-- markdownlint-enable MD034 -->

### レポートスイートの分析

1. レポートスイートを分析し、移行するレポートスイートを決定するには、**[!UICONTROL データ設定と収集]**/**[!UICONTROL レポートスイート]** に移動し、「**[!UICONTROL 分析]**」をクリックします。

   ![ レポートスイートのリスト ](assets/an_inv_rs.png)

   | 要素 | 説明 |
   | --- | --- |
   | 名前 | レポートスイートの名前 |
   | ID | レポートスイート ID （rsid）。 英数字文字のみ含めることができる一意の ID を指定します。この ID は作成後は変更できません。アドビによって設定される必須の ID プレフィックスも変更できません。 |
   | 発生件数 (過去 90 日間) |  |
   | 指標 | How |
   | ディメンション |  |
   | Analytics for Target (A4T) は有効になっています |  |
   | マーケティングチャネルは有効になっています |  |
   | Source Connector 有効 | フォローする |
   | カレンダータイプ | 詳しくは、[ カスタムカレンダー ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) を参照してください。 |

1. 注目すべき

### CSV に書き出し

1. レポートスイートのリストを.csv ファイルに書き出すには、「**[!UICONTROL CSV に書き出し]**」をクリックします。

1. .csv ファイルがダウンロードフォルダーに表示されます。

1. を開き、デバイスのスプレッドシートアプリケーションで保存します。


## ユーザー管理 {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="ユーザー管理"
>abstract="このセクションには、Adobe Analytics 環境内のユーザーの数が表示されます。"

<!-- markdownlint-enable MD034 -->

ユーザー管理は、Analytics インベントリの今後のリリースで使用できるようになります。