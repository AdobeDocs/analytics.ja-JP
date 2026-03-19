---
title: AMO EF ID
description: Adobe Media Optimizer の EF ID。Adobe Advertising統合で使用されます。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 4%

---

# AMO EF ID

**[!UICONTROL AMO EF ID]** は、Adobe Advertising統合で使用される広告クリック識別子です。 これは、Adobe Advertisingが訪問者レベルでアクティビティをオンラインクリックまたは広告露出に関連付けるために使用する一意のトークンです。 [Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview) 統合を有効にすると、ディメンションが自動的に作成されます。

## このディメンションへのデータ入力

このディメンションは、次の複数の方法で値を収集します。

* クリックスルートラフィックの場合、データは、通常、広告ドリブン型トラフィックがサイトに入るページにある `ef_id` ページ URL[ の ](page-url.md) クエリ文字列パラメーターから収集されます。
* クリックスルートラフィックは、URL にトラッキングコードが含まれていないが、Adobe Advertising JavaScriptによって過去 2 分以内にクリックが検出された場合にもキャプチャできます。
* サポートされているビュースルートラフィックの場合、Adobe Advertisingは、追加の ID （`SDID`）を使用してバックエンドの値を補完します。

>[!NOTE]
>
>EF ID では大文字と小文字が区別されます。 実装によって URL トラッキングが強制的に小文字に変換される場合、Adobe Advertisingは EF ID を認識しません。

## ディメンション項目

Dimension商品には、サポートされている広告ネットワークで生成された広告クリック識別情報が含まれます。 文字列の形式は、生成したネットワークとチャネルによって異なります。

### Google Ads 検索広告

```text
{gclid}:G:{s}
```

* **`gclid`**:Google クリック ID （GCLID）。
* **`s`**：ネットワークの種類（検索用に `"s"`）。

### Microsoft Advertising検索広告

```text
{msclkid}:G:{s}
```

* **`msclkid`**:Microsoft クリック ID （MSCLKID）。
* **`s`**：ネットワークの種類（検索用に `"s"`）。

### 他の検索エンジンでの広告および検索広告の表示

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**:Adobe Advertising訪問者 ID （サーファー ID とも呼ばれます）。
* **`ts`**:Adobe Advertisingによって生成されたタイムスタンプ。
* **`channel`**：クリックまたは露出に関係するチャネルのタイプ
   * **`d`**:DSP ディスプレイ広告のクリック（表示のクリックスルー）。
   * **`i`**:DSP ディスプレイ広告のインプレッション（ビュースルーの表示）。
   * **`s`**：検索広告のクリック（検索クリックスルー）。

### 例

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
