---
title: 広告プラットフォームの同意
description: サードパーティ広告プロバイダーの広告同意の設定を参照してください。
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 3%

---

# 広告プラットフォームの同意

「広告プラットフォームの同意」 [ ディメンション ](overview.md)には、GoogleやMetaなどのサードパーティの広告プロバイダーにデータを送信するために同意が収集されているかどうかが表示されます。

現在、このディメンションはGoogleにのみ使用されています。 欧州のプライバシー規制であるデジタル市場法（DMA）により、Googleでは、サーバーに送信されたデータと欧州で収集されたデータに、同意の有無を示す必要があることを義務付けています。 一部のAnalyticsのお客様は、Adobe Advertisingを介してイベントデータをコンバージョンイベントとしてGoogleに送信します。

将来的には、このディメンションを使用して、他のサードパーティの広告プロバイダーの追加同意情報のエンコーディングをサポートすることもできます。

## このディメンションへのデータ入力

このディメンションは、次の[ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)からデータを収集します

* `contextData.['adConsent']`

Googleの同意フィールドに関連する値をコンテキストデータ変数に入力します

* `ad_user_data` （1人目の文字）および
* `ad_personalization` （2文字目）。

詳しくは、Google Ads API リファレンス ](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent)の[同意を参照してください。

これらの各フィールドに指定できる値は次のとおりです。

| 値 | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | 広告ユーザーデータのGoogleへの同意の付与。 | 広告のパーソナライズのためにGoogleに同意します。 |
| `N` | 広告ユーザーデータについてGoogleへの同意を拒否する。 | 広告のパーソナライズについて、Adobe Googleに完全な同意を得る。 |
| `U` | 未指定。 | 未指定。 |

次の例では、広告のパーソナライゼーションではなく、広告ユーザーデータに対してGoogleに同意を付与します。

```
contextData.['adConsent'] = "YN..."
```

1番目と2番目の文字を超える文字は現在無視されています。

## データの活用

収集した広告の同意データを使用できます。

* データフィード：広告同意データは、`dataprivacydmaconsent` [列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)を使用して利用できます。
* Data Warehouse レポート：広告同意データは、**[!UICONTROL 広告プラットフォームの同意]** ディメンションを使用して利用できます。

このコンテキストデータ変数を実装するロジックは、組織によって決まります。 値は設定されたヒットを超えて保持されないので、各ページにコンテキストデータ変数を設定する必要があります。

Adobe Advertisingを通じてAdobe Analyticsからコンバージョンイベントとして広告データをGoogleに送信する場合は、Adobe Advertising チームに相談して統合を支援してください。

詳しくは、「[ プライバシーレポート ](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md)」を参照してください。
