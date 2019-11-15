---
description: このガイドラインに従うと、同じ cookie ドメインを使用して、様々なタイプの導入で訪問を追跡できるようになります。
keywords: Analytics Implementation
solution: Analytics
title: 実装のガイドライン
topic: Developer and implementation
uuid: 2917f4af-19bd-4666-ae4b-056e7e33f642
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 実装のガイドライン

このガイドラインに従うと、同じ cookie ドメインを使用して、様々なタイプの導入で訪問を追跡できるようになります。

* **RSID：**[!UICONTROL レポートスイート ID]
* **VNS：**（訪問者ネームスペース）[!DNL 2o7.net]訪問者 ID[!DNL omtrdc.net] cookie を保存するために使用される [!UICONTROL  または ] のサブドメイン。
* **COOKIEDOMAIN：** VNS + trackingServer。これらはデータセンターと RDC 設定によって大きく異なります。[データ収集ドメインについて](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) 、不明な点はカスタマーケアにお問い合わせください。

## JavaScript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## ハードコーディングされたイメージリクエスト

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->
```

ファーストパーティ cookie の導入を使用している場合、`VNS.COOKIEDOMAIN.net` は、使用しているファーストパーティ cookie ドメインで置き換えることができます。例えば、`adobe.com` でファーストパーティ cookie を使用している場合は、`metrics.adobe.com` などと置き換えることができます。
