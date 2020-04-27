---
description: Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。
title: Power BI Desktop への発行済みアセットの取り込み
uuid: ef47d5c7-31e0-44fc-a792-bc9d12bb089e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Power BI Desktop への発行済みアセットの取り込み

Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。

## 前提条件 {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* 最新バージョン（2017 年 4 月リリース）の Power BI Desktop をインストールしておく必要があります。
* この手順では、Report Builder でフォーマットされたテーブルまたはリクエストを Power BI サービスに既に発行していることを前提としています。

## プロセス {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

2017 年 4 月の Power BI Desktop のアップデートで、Power BI サービスのデータセットに接続する機能が Microsoft によってリリースされました。この機能を使用すると、クラウドに発行済みの既存のデータセットから新しいレポートを作成できます。この機能を活用すれば、チームでの共同作業を円滑にし、重複作業を減らすことができます。

1. Power BI Desktopで、// **[!UICONTROL File]** に移 **[!UICONTROL Options and settings]** 動しま **[!UICONTROL Options]** す **[!UICONTROL Preview features.]**
1. を有効にし **[!UICONTROL Power BI Service Live Connection]** て、をクリックしま **[!UICONTROL OK]**&#x200B;す。 ![](assets/bi-preview-features.png)

1. Power BI Desktop を再起動します。
1. デスクトップを再起動したら、//に移 **[!UICONTROL Home]** 動し **[!UICONTROL Get Data]** ます **[!UICONTROL More...]**。
1. を検索し、を選択しま **[!UICONTROL Power BI service]**&#x200B;す。
1. /の下 **[!UICONTROL Microsoft Power BI service]** で、 **[!UICONTROL My Workspace]**&#x200B;以前にReport Builderから公開したデータセットを選択します。

詳しくは、[Microsoft のブログ投稿](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/)を参照してください。
