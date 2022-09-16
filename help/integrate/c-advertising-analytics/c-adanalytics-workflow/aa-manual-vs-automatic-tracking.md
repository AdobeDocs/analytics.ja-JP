---
description: トラッキングにより、Adobe Analytics の実装による検索エンジンデータの追跡方法が決まります。これは、検索エンジンのデータで Adobe Analytics のデータを適切に拡張するために必要な手順です。
title: トラッキング：手動モードと自動モード
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 100%

---

# トラッキング：手動モードと自動モード

トラッキングにより、Adobe Analytics の実装による検索エンジンデータの追跡方法が決まります。これは、検索エンジンのデータで Adobe Analytics のデータを適切に拡張するために必要な手順です。

以下に、Advertising Analytics トラッキングテンプレートの実装方法に関する概要ビデオを示します。

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

自動モードと手動モードの 2 つのトラッキングモードがサポートされています。

## 自動モードのトラッキング {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

自動モードでは、Advertising Cloud Engine によって検索エンジンの処理方法が決定されます。これはもっともシンプルな方法ですが、統合されたデータセットの品質が最良ではなくなる可能性があります。

そのため、アカウント設定を保存するには自動モードの選択時に承認のチェックボックスをチェックする必要があります。

「自動モード」で検索エンジンのアカウントを設定するには、以下の作業を行う責任があります。

* `s_kwcid` パラメーターおよび値がアカウントのトラッキングテンプレート、または追加されるアカウント内のランディングページ URL に追加されます。これは、URL の最後に挿入されます。Web サーバーで URL の最後に特定の key=value ペアが必要な場合、または URL の新しい key=value ペアをサポートするための更新が必要な場合は、追加のアクションが必要になる場合があります。**ユーザーの責任のもとに、追加された URL パラメーターが最終的なランディングページまで適切に保持されるようにする必要があります。**
* 加えて、キーワードを `s_kwcid` 値の一部としてランディング URL に追加できます。特殊文字や記号が含まれる場合は、Web サーバーでそれらの文字がサポートされていることを確認してください。例：一般的な特殊文字の例は「+」です。これは、「絞り込み部分一致」キーワードに使用されます。

>[!IMPORTANT]
>
>[コンテンツセキュリティポリシー](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html?lang=ja)に `s_kwcid` パラメーターを追加する必要があるかどうかを確認します。

## 手動モードのトラッキング {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

手動モードでは、検索エンジンデータが Advertising Analytics データ統合プロセスによってどのように処理されるかを指定する必要があります。

### Google アカウントへの手動トラッキングの追加 {#section_41C1EB1AEB034544A5BC291F53C05C67}

Google アカウントに追加する必要がある文字列を以下に示します。アカウント全体で使用されるすべてのトラッキングテンプレートに文字列を追加する必要があります。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` の値（下記の&#x200B;**太字**&#x200B;部分）は総称であり、**固有のアカウント ID 文字列に置き換える必要があります**。使用する固有のアカウント ID 文字列は、「トラッキング」セクションのアカウント設定画面から取得できます。

**キャンペーンのトラッキング文字列：**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![](assets/Google.png)

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

URL がリダイレクトを経由し、値「unescapedlpurl」を使用しない場合は、文字列がリダイレクトを通じて最終的なランディングページ URL まで保持されるように十分な時間エンコードする必要があります。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Bing アカウントへの手動トラッキングの追加 {#section_094F8ACA493C4D65B1F54A695558EBF2}

Bing アカウントに追加する必要がある文字列を以下に示します。アカウント全体で使用されるすべての最終 URL サフィックスに文字列を追加する必要があります。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` の値（下記の&#x200B;**太字**&#x200B;部分）は総称であり、**固有のアカウント ID 文字列に置き換える必要があります**。使用する固有のアカウント ID 文字列は、「トラッキング」セクションのアカウント設定画面から取得できます。

**キャンペーンのトラッキング文字列：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

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

URL がリダイレクトを経由し、値「unescapedlpurl」を使用しない場合は、文字列がリダイレクトを通じて最終的なランディングページ URL まで保持されるように十分な時間エンコードする必要があります。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
