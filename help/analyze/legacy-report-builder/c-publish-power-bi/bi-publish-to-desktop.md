---
description: Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。
title: Power BI Desktop への発行済みアセットの取り込み
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 60%

---

# Power BI Desktop への発行済みアセットの取り込み

{{legacy-arb}}

Report Builder から発行されたアセットを Power BI Desktop に取り込む方法を説明します。

## 前提条件 {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* 最新のPower BI Desktop バージョン（2017年4月リリース）がインストールされている必要があります
* このプロセスでは、Power BI サービスにReport Builder形式のテーブルまたはリクエストを既に公開していることを前提としています。

## プロセス {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Power BI Desktopの2017年4月アップデートで、MicrosoftはPower BI サービスのデータセットに接続する機能をリリースしました。 この機能を使用すると、クラウドに公開済みの既存のデータセットに関する新しいレポートを作成できます。 この機能を利用することで、より優れたコラボレーションが可能になり、チーム全体で重複する作業を減らすことができます。

1. Power BI Desktop で、**[!UICONTROL ファイル]**／**[!UICONTROL オプションと設定]**／**[!UICONTROL オプション]**／**[!UICONTROL プレビュー機能]**&#x200B;に移動します。
1. 「**[!UICONTROL Power BI サービスライブ接続]**」をオンにして、「**[!UICONTROL OK]**」をクリックします。 ![「Power BI サービスライブ接続」をクリックしてから、「OK」をクリックします。](assets/bi-preview-features.png)

1. Power BI Desktop を再起動します。
1. Power BI Desktop を再起動したら、**[!UICONTROL ホーム]**／**[!UICONTROL データを取得]**／**[!UICONTROL さらに表示...]** に移動します。
1. 「**[!UICONTROL Power BI サービス]**」を検索して選択します。
1. **[!UICONTROL Microsoft Power BI サービス]**／**[!UICONTROL マイワークスペース]**&#x200B;で、以前に Report Builder から発行したデータセットを選択します。

詳しくは、[Microsoft のブログ投稿](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/)を参照してください。
