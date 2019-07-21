---
description: トラッキングにより、Adobe Analytics の実装による検索エンジンデータの追跡方法が決まります。これは、検索エンジンのデータで Adobe Analytics のデータを適切に拡張するために必要な手順です。
seo-description: トラッキングにより、Adobe Analytics の実装による検索エンジンデータの追跡方法が決まります。これは、検索エンジンのデータで Adobe Analytics のデータを適切に拡張するために必要な手順です。
seo-title: トラッキングマニュアルモードと自動モード
title: トラッキングマニュアルモードと自動モード
uuid: c6ce7901-7b65-48b6- b65f- f29cc47b7454
translation-type: tm+mt
source-git-commit: 463e28e9d710cc41e4ab4ace5e3861b8ae8fbdcc

---


# トラッキング：手動モードと自動モード

トラッキングにより、Adobe Analytics の実装による検索エンジンデータの追跡方法が決まります。これは、検索エンジンのデータで Adobe Analytics のデータを適切に拡張するために必要な手順です。

自動モードと手動モードの 2 つのトラッキングモードがサポートされています。

## 自動モードのトラッキング {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

自動モードでは、Advertising Cloud Engine によって検索エンジンの処理方法が決定されます。これはもっともシンプルな方法ですが、統合されたデータセットの品質が最良ではなくなる可能性があります。

そのため、アカウント設定を保存するには自動モードの選択時に承認のチェックボックスをチェックする必要があります。


検索エンジンアカウントを「自動モード」で設定するには、次の操作を行う必要があります。

* 「s_kwcid」のパラメーターおよび値がアカウントのトラッキングテンプレート、または追加されるアカウント内のランディングページ URL に追加されます。これは、URL の最後に挿入されます。ウェブサーバーに特定の key=value ペアが URL の最後に必要な場合や、URLの で新しい key=value ペアをサポートするための更新が必要な場合は、ご自身で追加の作業を行う必要がある場合があります。**ユーザーの責任のもとに、追加された URL パラメーターが最終的なランディングページまで適切に保持されるようにする必要があります。**
* 加えて、キーワードを「s_kwcid」値の一部としてランディング URL に追加できます。特殊文字や記号が含まれる場合は、ウェブサーバーでそれらの文字がサポートされていることを確認してください。例：一般的な特殊文字の例は「+」です。これは、「絞り込み部分一致」キーワードに使用されます。

## 手動モードのトラッキング {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

手動モードでは、検索エンジンデータが Advertising Analytics データ統合プロセスによってどのように処理されるかを指定する必要があります。

### Google アカウントへの手動トラッキングの追加 {#section_41C1EB1AEB034544A5BC291F53C05C67}

Google アカウントに追加する必要がある文字列を以下に示します。アカウント全体で使用されるすべてのトラッキングテンプレートに文字列を追加する必要があります。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` 値（下 **の太字** ）は汎用で、特定のアカウントID文字列に置き換える **必要**&#x200B;があります。使用する固有のアカウント ID 文字列は、「トラッキング」セクションのアカウント設定画面から取得できます。

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

**`{lpurl}`追加のURLパラメーターを使用**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**サードパーティ（DoubleClick）`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**サードパーティ（DoubleClick）`{lpurl}`**

URL がリダイレクトを経由し、値「unescapedlpurl」を使用しない場合は、文字列がリダイレクトを通じて最終的なランディングページ URL まで保持されるように十分な時間エンコードする必要があります。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Bing アカウントへの手動トラッキングの追加 {#section_094F8ACA493C4D65B1F54A695558EBF2}

Bing アカウントに追加する必要がある文字列を以下に示します。アカウント全体で使用されるすべてのトラッキングテンプレートに文字列を追加する必要があります。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` 値（下 **の太字** ）は汎用で、特定のアカウントID文字列に置き換える **必要**&#x200B;があります。使用する固有のアカウント ID 文字列は、「トラッキング」セクションのアカウント設定画面から取得できます。

**キャンペーンのトラッキング文字列：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

様々なトラッキングテンプレート形式によるトラッキングコードの例：

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}`
```

**`{lpurl}`追加のURLパラメーターを使用**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**3rd- party（doubleClick）'{uncapesedlpurl}**

```https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}

```

**サードパーティ（DoubleClick）`{lpurl}`**

URL がリダイレクトを経由し、値「unescapedlpurl」を使用しない場合は、文字列がリダイレクトを通じて最終的なランディングページ URL まで保持されるように十分な時間エンコードする必要があります。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
