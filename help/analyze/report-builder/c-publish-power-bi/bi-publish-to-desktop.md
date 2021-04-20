---
description: Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。
title: Power BI Desktop への発行済みアセットの取り込み
uuid: ef47d5c7-31e0-44fc-a792-bc9d12bb089e
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 98%

---


# Power BI Desktop への発行済みアセットの取り込み

Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。

## 前提条件 {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* 最新バージョン（2017 年 4 月リリース）の Power BI Desktop をインストールしておく必要があります。
* この手順では、Report Builder でフォーマットされたテーブルまたはリクエストを Power BI サービスに既に発行していることを前提としています。

## プロセス {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

2017 年 4 月の Power BI Desktop のアップデートで、Power BI サービスのデータセットに接続する機能が Microsoft によってリリースされました。この機能を使用すると、クラウドに発行済みの既存のデータセットから新しいレポートを作成できます。この機能を活用すれば、チームでの共同作業を円滑にし、重複作業を減らすことができます。

1. Power BI Desktop で、**[!UICONTROL ファイル]**／**[!UICONTROL オプションと設定]**／**[!UICONTROL オプション]**／**[!UICONTROL プレビュー機能]**&#x200B;に移動します。
1. 「**[!UICONTROL Power BI サービスライブ接続]**」をオンにして、「**[!UICONTROL OK]**」をクリックします。![](assets/bi-preview-features.png)

1. Power BI Desktop を再起動します。
1. Power BI Desktop を再起動したら、**[!UICONTROL ホーム]**／**[!UICONTROL データを取得]**／**[!UICONTROL さらに表示...]** に移動します。
1. 「**[!UICONTROL Power BI サービス]**」を検索して選択します。
1. **[!UICONTROL Microsoft Power BI サービス]**／**[!UICONTROL マイワークスペース]**&#x200B;で、以前に Report Builder から発行したデータセットを選択します。

詳しくは、[Microsoft のブログ投稿](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/)を参照してください。
