---
description: トラッキングタイプは、Adobe Analytics実装が検索エンジンデータを追跡する方法を決定します。 このトラッキングタイプは、Adobe Analytics データを検索エンジンデータで適切に拡張するために必要な手順です。
title: トラッキングタイプ
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 28%

---

# トラッキングタイプ

トラッキングタイプは、Adobe Analytics実装が検索エンジンデータを追跡する方法を決定します。 このトラッキングタイプは、Adobe Analytics データを検索エンジンデータで適切に拡張するために必要な手順です。

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/ad-cloud/implementing-tracking-templates-into-search-engines)

-->

[!UICONTROL  自動 ] と [!UICONTROL  手動 ] の 2 つのトラッキングモードがサポートされています。

## [!UICONTROL  自動 ] トラッキング {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

[!UICONTROL  自動 ] トラッキング機能を使用すると、Advertising Cloud エンジンは、検索エンジンデータの処理方法を決定できます。 自動トラッキングはよりシンプルなアプローチですが、最適な統合データセットにならない場合があります。

そのため、アカウント設定を保存する前に、「**[!UICONTROL 自動]**」を選択する際に確認チェックボックスをオンにする必要があります。

「**[!UICONTROL 自動]**」タイプの検索エンジンアカウントを設定するには、次の操作を行う必要があります。

* `s_kwcid` パラメーターと値が、追加するアカウントのアカウントトラッキングテンプレートまたはランディングページ URL に追加されます。 このパラメーターと値は、URL の末尾に挿入されます。 Web サーバーで URL の末尾に特定の `key=value` のペアが必要な場合は、追加のアクションが必要になる場合があります。 または、URL で新しい `key=value` のペアをサポートするように更新します。 追加した URL パラメーターが最終的なランディングページに正しく保持されるようにするには、ユーザーの責任です。
* 加えて、キーワードを `s_kwcid` 値の一部としてランディング URL に追加できます。特殊文字やシンボルが含まれる場合は、web サーバーでそれらの文字がサポートされていることを確認してください。例えば、一般的な特殊文字は `+` で、「部分一致で変更された」キーワードで使用されます。

>[!IMPORTANT]
>
>[コンテンツセキュリティポリシー](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp)に `s_kwcid` パラメーターを追加する必要があるかどうかを確認します。

## 手動トラッキング {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

手動トラッキングを使用すると、Advertising Analytics データ統合プロセスによる検索エンジンデータの処理方法を指定できます。

### Google アカウントへの手動トラッキングの追加 {#section_41C1EB1AEB034544A5BC291F53C05C67}

Google アカウントに追加する必要がある文字列を以下に示します。アカウント全体で使用されるすべてのトラッキングテンプレートに文字列を追加する必要があります。

>[!IMPORTANT]
>
>*`<Advertising Analytics ID>`* の値（下記の&#x200B;**太字**&#x200B;部分）は総称であり、**固有のアカウント ID 文字列に置き換える必要があります**。特定のアカウント ID 文字列は、「[!UICONTROL  トラッキング ]」セクションのアカウント画面から取得できます。

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

最終的なランディングページ URL へのリダイレクトを通して文字列が保持されるようにするには、文字列を十分にエンコードする必要があります。

* url がリダイレクトを経由する場合、および
* は、「unescapedlpurl」値を使用していません。


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Microsoft Advertising アカウントへの手動トラッキングの追加 {#section_094F8ACA493C4D65B1F54A695558EBF2}

Microsoft Advertising アカウントに追加する必要がある文字列を以下に示します。 アカウント全体で使用されるすべての最終 URL サフィックスに文字列を追加する必要があります。

>[!IMPORTANT]
>
>_`<Advertising Analytics ID>`_の値（下記の&#x200B;**太字**部分）は総称であり、**固有のアカウント ID 文字列に置き換える必要があります**。特定のアカウント ID 文字列は、「トラッキング」セクションのアカウント画面から取得できます。

**キャンペーンのトラッキング文字列：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![ トラッキングコードパラメーターの追加 ](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

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

最終的なランディングページ URL へのリダイレクトを通して文字列が保持されるようにするには、文字列を十分にエンコードする必要があります。

* url がリダイレクトを経由する場合、および
* は、「unescapedlpurl」値を使用していません。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
