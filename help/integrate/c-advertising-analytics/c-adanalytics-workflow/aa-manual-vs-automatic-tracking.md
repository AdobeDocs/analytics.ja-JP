---
description: トラッキングタイプは、Adobe Analyticsの実装が検索エンジンデータをどのようにトラッキングするかを決定します。 このトラッキングタイプは、Adobe Analytics データを検索エンジンデータで適切に拡張するために必要な手順です。
title: トラッキングタイプ
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
TQID: https://experienceleague.adobe.com/QKLoFYVeGTZyOPsFKWPVUtmQ7oyYTnw05s47XIn6n8c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 584
ht-degree: 28%

---

# トラッキングタイプ

トラッキングタイプは、Adobe Analyticsの実装が検索エンジンデータをどのようにトラッキングするかを決定します。 このトラッキングタイプは、Adobe Analytics データを検索エンジンデータで適切に拡張するために必要な手順です。

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/integrations/ad-cloud/implementing-tracking-templates-into-search-engines)

-->

2つのトラッキングモードがサポートされています：[!UICONTROL 自動]と[!UICONTROL 手動]。

## [!UICONTROL 自動]追跡 {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

[!UICONTROL 自動] トラッキングを使用すると、Adobe Advertising エンジンが検索エンジンデータの処理方法を決定できます。 自動トラッキングは最もシンプルなアプローチですが、最良の統合データセットにはつながらない可能性があります。

したがって、アカウント設定を保存する前に、**[!UICONTROL 自動]**&#x200B;を選択する際に、確認確認チェックボックスをオンにする必要があります。

**[!UICONTROL 自動]** タイプの検索エンジンアカウントを設定するには、次の操作を実行する必要があります。

* `s_kwcid` パラメーターと値が、追加するアカウントのアカウント トラッキング テンプレートまたはランディングページ URLに追加されます。 このパラメーターと値は、URLの最後に挿入されます。 Web サーバーがURLの末尾に特定の`key=value` ペアを必要とする場合、追加のアクションが必要になる場合があります。 または、URL内の新しい`key=value` ペアをサポートするための更新です。 追加されたURL パラメーターが最終的なランディングページに正しく保持されるように確認するのは、お客様の責任です。
* 加えて、キーワードを `s_kwcid` 値の一部としてランディング URL に追加できます。 特殊文字やシンボルが含まれる場合は、web サーバーでそれらの文字がサポートされていることを確認してください。 例えば、共通の特殊文字は`+`で、「Broad Match Modified」キーワードで使用されます。

>[!IMPORTANT]
>
>[コンテンツセキュリティポリシー](https://experienceleague.adobe.com/ja/docs/id-service/using/reference/csp)に `s_kwcid` パラメーターを追加する必要があるかどうかを確認します。

## 手動トラッキング {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

手動トラッキングを使用すると、Advertising Analytics データ統合プロセスで検索エンジンデータを処理する方法を指定できます。

### Google アカウントに手動トラッキングを追加する {#section_41C1EB1AEB034544A5BC291F53C05C67}

Google アカウントに追加する必要がある文字列を以下に示します。 アカウント全体で使用されるすべてのトラッキングテンプレートに文字列を追加する必要があります。

>[!IMPORTANT]
>
>*`<Advertising Analytics ID>`* の値（下記の&#x200B;**太字**&#x200B;部分）は総称であり、**固有のアカウント ID 文字列に置き換える必要があります**。 [!UICONTROL &#x200B; トラッキング &#x200B;] セクションのアカウント画面から、特定のアカウント ID文字列を取得できます。

**キャンペーンのトラッキング文字列：**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

様々なトラッキングテンプレート形式によるトラッキングコードの例：

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`と追加の URL パラメーター**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**サードパーティ（ダブルクリック）`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**サードパーティ（ダブルクリック）`{lpurl}`**

文字列が最後のランディングページ URLへのリダイレクトを通じて保持されるようにするには、文字列を十分にエンコードする必要があります。

* URLがリダイレクトを経由する場合、
* は「unescapedlpurl」値を使用していません。


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Microsoft Advertising アカウントに手動トラッキングを追加する {#section_094F8ACA493C4D65B1F54A695558EBF2}

Microsoft Advertising アカウントに追加する必要がある文字列を以下に示します。 アカウント全体で使用されるすべての最終 URL サフィックスに文字列を追加する必要があります。

>[!IMPORTANT]
>
>_`<Advertising Analytics ID>`_の値（下記の&#x200B;**太字**&#x200B;部分）は総称であり、**固有のアカウント ID 文字列に置き換える必要があります**。 「トラッキング」セクションのアカウント画面から、特定のアカウント ID文字列を取得できます。

**キャンペーンのトラッキング文字列：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![&#x200B; トラッキングコードパラメーターを追加](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

様々な最終 URL 形式によるトラッキングコードの例：

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`と追加の URL パラメーター**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**サードパーティ（ダブルクリック）`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**サードパーティ（ダブルクリック）`{lpurl}`**

文字列が最後のランディングページ URLへのリダイレクトを通じて保持されるようにするには、文字列を十分にエンコードする必要があります。

* URLがリダイレクトを経由する場合、
* は「unescapedlpurl」値を使用していません。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
