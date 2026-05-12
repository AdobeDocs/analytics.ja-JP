---
title: ストリーミングメディアサービスとディメンション
description: レポートスイートで[!UICONTROL &#x200B; メディア広告]を有効にした場合に使用できるディメンション。
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
TQID: https://experienceleague.adobe.com/5d5RQ-2dkRD-R5U0iVyApP7WdCH2O1Rsk-qlPLYJm9c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 1be0f3577403db7cf9bd40ef9e7c4bfcfa6c0b17
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 2%

---

# ストリーミングメディアサービスとディメンション

ストリーミングメディアサービスとディメンションは、ストリーミングメディア収集ライブラリを通じて収集されたデータに対する追加のレポート機能を提供します。 これらのディメンションには、**[!UICONTROL Adobe Analytics for Streaming Media アドオン]**&#x200B;が必要です。 詳しくは、Adobe アカウントチームにお問い合わせください。

これらのディメンションを使用するには、レポートスイートの[[!UICONTROL Media Reporting]](/help/admin/tools/manage-rs/edit-settings/media-management.md)で&#x200B;**[!UICONTROL Media Ads]**&#x200B;を有効にします。

次のディメンションを使用できます。

* [[!UICONTROL Ad]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad)
* [[!UICONTROL &#x200B; ポッド位置の広告]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-in-pod-position)
* [[!UICONTROL 広告の長さ（変数） &#x200B;]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-length)
* [[!UICONTROL 広告名（変数） &#x200B;]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-name)
* [[!UICONTROL &#x200B; プレイヤー名]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-player-name)
* [[!UICONTROL 広告ポッド &#x200B;]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-pod)
* [[!UICONTROL 広告主]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/advertiser)
* [[!UICONTROL キャンペーン ID]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/campaign-id)

上記のディメンションに加えて、Adobeは次の分類ディメンションを自動的に作成します。 これらのディメンションを使用するレポートを表示するには、分類データをアップロードする必要があります。

| 分類名 | 親ディメンション |
| --- | --- |
| [[!UICONTROL &#x200B; アセット ID]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/asset-id) | [[!UICONTROL コンテンツ]](sm-core.md) |
| [[!UICONTROL &#x200B; コンテンツの評価]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/content-rating) | [[!UICONTROL コンテンツ]](sm-core.md) |
| [[!UICONTROL 最初のエア日]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/first-air-date) | [[!UICONTROL コンテンツ]](sm-core.md) |
| [[!UICONTROL 最初のデジタル日付]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/first-digital-date) | [[!UICONTROL コンテンツ]](sm-core.md) |
| [[!UICONTROL 広告の長さ]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-length) | [!UICONTROL Ad] |
| [[!UICONTROL 広告名]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-name) | [!UICONTROL Ad] |
| [[!UICONTROL Creative ID]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/creative-id) | [!UICONTROL Ad] |
| [[!UICONTROL &#x200B; ポッド名]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/pod-name) | [!UICONTROL 広告ポッド &#x200B;] |
| [[!UICONTROL &#x200B; ポッドの位置]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/pod-position) | [!UICONTROL 広告ポッド &#x200B;] |

対応する指標については、[&#x200B; ストリーミングメディアサービスと指標](../metrics/sm-ads.md)を参照してください。
