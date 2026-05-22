---
title: AMO EF ID
description: Adobe Advertising統合で使用されるAdobe Media Optimizer EF ID。
feature: Dimensions
exl-id: 129b0235-9b00-4d75-8b02-0443dfdef091
TQID: 'https://experienceleague.adobe.com/gye9CwGtFwPppmrTbpB5CErZjIdKeAtSPr6VPUtPod4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 4%

---

# AMO EF ID

**[!UICONTROL AMO EF ID]**&#x200B;は、Adobe Advertising統合で使用される広告クリック IDです。 これは、Adobe Advertisingが、アクティビティをオンラインクリックや広告露出と、訪問者レベルで関連付けるために使用する一意のトークンです。 ディメンションは、[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)統合を有効にすると自動的に作成されます。

## このディメンションへのデータ入力

このディメンションは、複数の方法で値を収集します。

* クリックスルートラフィックの場合、データは[&#x200B; ページ URL](page-url.md)の`ef_id` クエリ文字列パラメーターから収集されます。通常は、広告駆動型トラフィックがサイトに入るページ上に収集されます。
* クリックスルートラフィックは、URLにトラッキングコードが含まれていない場合にもキャプチャできますが、Adobe Advertising JavaScriptでは、前の2分以内にクリックが検出されます。
* サポートされているビュースルートラフィックの場合、Adobe Advertisingはバックエンドの値を補足ID （`SDID`）を使用して補完します。

>[!NOTE]
>
>EF IDでは、大文字と小文字が区別されます。 実装でURL トラッキングを小文字に強制する場合、Adobe AdvertisingはEF IDを認識しません。

## ディメンション項目

Dimensionの項目には、サポートされている広告ネットワークによって生成された広告クリック識別子が含まれます。 文字列形式は、それを生成したネットワークとチャネルによって異なります。

### Google Adsの検索広告

```text
{gclid}:G:{s}
```

* **`gclid`**: Google クリック ID （GCLID）。
* **`s`**: ネットワークの種類（`"s"`検索用）。

### Microsoft Advertisingの検索広告

```text
{msclkid}:G:{s}
```

* **`msclkid`**: Microsoft クリック ID （MSCLKID）。
* **`s`**: ネットワークの種類（`"s"`検索用）。

### 他の検索エンジンに広告や検索広告を表示する

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**: Adobe Advertising訪問者ID。サーファーIDとも呼ばれます。
* **`ts`**: Adobe Advertisingによって生成されたタイムスタンプ。
* **`channel`**: クリックまたは露出を担当するチャネルタイプ：
   * **`d`**: DSP ディスプレイ広告（表示クリックスルー）をクリックします。
   * **`i`**: DSP ディスプレイ広告（表示ビュースルー）のインプレッション。
   * **`s`**：検索広告（検索クリックスルー）をクリックします。

### 例

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
