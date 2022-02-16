---
description: Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。
title: Power BI Desktop への発行済みアセットの取り込み
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Power BI Desktop への発行済みアセットの取り込み

Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。

## 前提条件  {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

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
